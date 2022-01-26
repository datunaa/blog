---
layout: post
title: Build your own DNS server on Linux
feature-img: "assets/img/feature-img/neural-network.jpg"
thumbnail: "assets/img/feature-img/neural-network.jpg"
tags: [dns, nameserver, ns]
---


# Learn how to use BIND to set up your own server for resolving domain names.

In the previous article in this two-part series, Introduction to the DNS (Domain Name System), I described how the DNS database is structured and how to configure name services on a client. I also listed and described some of the more common DNS records you are likely to encounter when building a name server or just trying to interpret the results of a **dig** command.

In this article, I show you how to build your own name server using [BIND](https://www.isc.org/downloads/bind/) (Berkeley Internet Name Domain). It is not as difficult as you might think, especially because you can do it in two stages.

In this article, you will start by learning how to create a caching name server, then you will move on and learn how to upgrade that to a complete primary (master) domain name server for your network, complete with forward and reverse zone files.


# Setting up a DNS server using BIND
Setting up a name server using BIND is quite straightforward, so I'll show you how to do so on any computer you might have available for experimentation. This little lab project will show you how to install and configure BIND on your computer as a caching name server, test it, then set it up as a primary name server with a zone file that you can use as a name resolver for your network or just for testing.

Setting up a name server on any GNU/Linux computer you have available is technically possible because it will not interfere with other hosts on the network or their operation. However, you should probably not do this on a computer that you do not own or have the right to modify unless you have explicit permission to do so.



# My setup

You only need one computer to perform all but one of the tasks in this lab project. I use this setup on my much more powerful ThinkPad because the name servers provided by DHCP (Dynamic Host Configuration Protocol) when I connect to non-home networks using either wired or wireless connections can sometimes be unreliable. To show that almost any host can perform well as a name server, I have tested this project on an old [ASUS EeePC 900](http://www.pcmag.com/article2/0,2817,2305998,00.asp) netbook.

I will use the private IP address of my ASUS for this project but you should use the IP address of the host that you are using.


# The hosts file
First, let's take a look at the **/etc/hosts** file. In its default state, there should only be two lines in the hosts file, the first two lines seen in Listing 1, below.


```yml
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6

# Lab hosts
192.168.25.1        server
192.168.25.21      host1
192.168.25.22      host2
192.168.25.23      host3
192.168.25.24      host4
```
Listing 1: You can maintain a simple hosts file to perform the function of a resolver in small networks.


Although you can add hostnames and their respective IP Addresses as shown in Listing 1, this is not an optimal solution to name services, especially when traveling. If there are other entries in your hosts file, you may need to comment them out for the duration of this project if they interfere with naming or IP addresses. Most of you will not have any entries other than the two default lines.


# Preparation
A caching name server can't replace your use of **/etc/hosts** to resolve hostnames on the internal network; however, compared to using an ISP or other public name server a caching name server can improve performance when resolving commonly used external names, such as www.cnn.com. The best part is that setting up a caching name server is quite easy.

Before starting, you should prepare by performing the following steps.

First, make backup copies of the files **/etc/hosts**, **/etc/named.conf**, **resolv.conf**, and **/etc/sysconfig/iptables**.

If they are not already installed, use your distribution's package manager to install the following BIND RPMs: bind, bind-chroot, and bind-utils. To enable your lab host to use the caching name server, you must add a name server line to point to your own host in /etc/resolv.conf. For example, if your lab host IP Address is 192.168.0.203, as is my epc, add the following line to the top of the name server list in /etc/resolv.conf:

```yml
name server         192.168.0.203
```

Be sure to use the IP Address of the host on which you are doing this project.

You could use the IP Address of your localhost, 127.0.0.1 instead of the external IP address. You should also comment out any lines pointing to other hosts as name servers. Be sure to save the revised **resolv.conf** file.

These changes will take effect immediately and no reboot or service restart is required. Now attempt to ping a common public host that does not block ICMP (Internet Control Message Protocol) packets; feel free to use my firewall, which is a [Raspberry Pi](https://opensource.com/life/16/3/firewall-your-home-network-raspberry-pi).

```yml
ping wally2.both.org
```

You should get an "unknown host" or "Name or service not known" error because you currently have no working DNS service or resolver defined in the resolv.conf file. Now use the **dig** command to see if name services is working.
```yml
dig wally2.both.com
```

You should get the error, "Connection timed out; no servers could be reached."



#Set up a caching name server

A caching name server is not an authoritative source for any domain. It simply caches the results of all name resolver requests from the network that it serves to speed up responses to future requests for the same remote host.

Note: The **named.conf** file is very particular about syntax and especially punctuation. Semicolons are used to delineate the end of an entry and the end of a stanza as well as the end of a line. Be sure to add them in correctly as shown in the samples.


For the initial setup of the caching name server making a couple modifications to the default **/etc/named.conf** file is necessary, so edit that file using your favorite editor. First, add the IP address of your local test host to the "listen-on port 53" line as shown in Listing 2, below. This enables **named** to listen on the external IP Address of your host, so that other computers can use it as a name server as well.


By default, BIND refers to the Internet's root name servers to locate the authoritative name servers for a domain. It is possible to specify other servers that are called "Forwarders" to which the local instance of BIND will send requests instead of the root servers. This does increase the possibility of DNS hijacking.

Add a "forwarders" line as shown below. This tells your caching DNS server where to obtain IP Addresses when they are not already cached locally. The IP Addresses in the listing below is for the [Google public DNS servers](https://developers.google.com/speed/public-dns/) You could use your local ISP or OpenDNS or some other public name server as your forwarder. It is not necessary to define any forwarders and, in that case, BIND would use the Internet root servers as defined in the file **/var/named/named.ca** to locate the authoritative name servers for domains if no forwarders are defined. But for this exercise, please define the forwarders as I have in Listing 2.



