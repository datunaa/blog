---
layout: post
title: find bugs on server
feature-img: "assets/img/feature-img/bug-finder.jpg"
thumbnail: "assets/img/feature-img/bug-finder.jpg"
tags: [hack, bug finder]
---

<div class="entry-content single-content">

<p>Customers usually turn to the internet to get information and buy products and services. Towards that end, most organizations have websites.<strong>Most websites store valuable information such as credit card numbers, email address and passwords, etc</strong>. This has made them targets to attackers. Defaced websites can also be used to communicate religious or political ideologies etc.</p>
<p>In this tutorial, we will introduce you toweb servers hacking techniques and how you can protect servers from such attacks.</p>
<p>In this tutorial, you will learn:</p>
<ul>
<li>
		<a href="#1">Web server vulnerabilities</a></li>
<li>
		<a href="#2">Types of Web Servers</a></li>
<li>
		<a href="#3">Types of Attacks against Web Servers</a></li>
<li>
		<a href="#4">Effects of successful attacks</a></li>
<li>
		<a href="#5">Web server attack tools</a></li>
<li>
		<a href="#6">How to avoid attacks on Web server</a></li>
<li>
		<a href="#7">Hacking Activity: Hack a WebServer</a></li>
</ul>
<h2><a id="1" data-lasso-id="199675" href="#"></a>Web server vulnerabilities</h2>
<p><strong>A web server is a program that stores files (usually web pages) and makes them accessible via the network or the internet</strong>. A web server requires both hardware and software. Attackers usually target the exploits in the software to gain authorized entry to the server. Let’s look at some of the common vulnerabilities that attackers take advantage of.</p>
<ul>
<li>
		<strong>Default settings</strong>– These settings such as default user id and passwords can be easily guessed by the attackers. Default settings might also allow performing certain tasks such as running commands on the server which can be exploited.</li>
<li>
		<strong>Misconfiguration</strong>of operating systems and networks – certain configuration such as allowing users to execute commands on the server can be dangerous if the user does not have a good password.</li>
<li>
		<strong>Bugs in the operating system and web servers</strong>– discovered bugs in the operating system or web server software can also be exploited to gain unauthorized access to the system.</li>
</ul>
<p>In additional to the above-mentioned web server vulnerabilities, the following can also led to unauthorized access</p>
<ul>
<li>
		<strong>Lack of security policy and procedures</strong>– lack of a security policy and procedures such as updating antivirus software, patching the operating system and web server software can create security loop holes for attackers.</li>
</ul>
<h2><a id="2" data-lasso-id="199676" href="#"></a>Types of Web Servers</h2>
<p>The following is a list of the common web servers</p>
<ul>
<li>
		<strong>Apache</strong>– This is the commonly used web server on the internet. It is cross platform but is it’s usually installed on Linux. Most<a href="/php-tutorials.html" onclick="ga('send', 'event', 'internal_linking', 'How to Hack a Web Server', 'How to Hack a Web Server');" data-lasso-id="199677"> PHP </a>websites are hosted on<a href="/apache.html" onclick="ga('send', 'event', 'internal_linking', 'How to Hack a Web Server', 'How to Hack a Web Server');" data-lasso-id="199678"> Apache </a>servers.</li>
<li>
		<strong>Internet Information Services (IIS)</strong>– It is developed by Microsoft. It runs on Windows and is the second most used web server on the internet. Most asp and aspx websites are hosted on IIS servers.</li>
<li>
		<strong>Apache Tomcat </strong>– Most Java server pages (JSP) websites are hosted on this type of web server.</li>
<li>
		<strong>Other web servers </strong>– These include Novell’s Web Server and IBM’s Lotus Domino servers.</li>
</ul>
<h2><a id="3" data-lasso-id="199679" href="#"></a>Types of Attacks against Web Servers</h2>
<p><strong>Directory traversal attacks</strong>– This type of attacks exploits bugs in the web server to gain unauthorized access to files and folders that are not in the public domain. Once the attacker has gained access, they can download sensitive information, execute commands on the server or install malicious software.</p><div class="code-block code-block-2" style="margin: 8px 0; clear: both;">
</div>

<ul>
<li>
		<strong>Denial of Service Attacks</strong>– With this type of attack, the web server may crash or become unavailable to the legitimate users.</li>
<li>
		<strong>Domain Name System Hijacking – </strong>With this type of attacker, the DNS setting are changed to point to the attacker’s web server. All traffic that was supposed to be sent to the web server is redirected to the wrong one.</li>
<li>
		<strong>Sniffing</strong>– Unencrypted data sent over the network may be intercepted and used to gain unauthorized access to the web server.</li>
<li>
		<strong>Phishing</strong>– With this type of attack, the attack impersonates the websites and directs traffic to the fake website. Unsuspecting users may be tricked into submitting sensitive data such as login details, credit card numbers, etc.</li>
<li>
		<strong>Pharming</strong>– With this type of attack, the attacker compromises the Domain Name System (DNS) servers or on the user computer so that traffic is directed to a malicious site.</li>
<li>
		<strong>Defacement</strong>– With this type of attack, the attacker replaces the organization’s website with a different page that contains the hacker’s name, images and may include background music and messages.</li>
</ul>
<h2><a id="4" data-lasso-id="199680" href="#"></a>Effects of successful attacks</h2>
<ul>
<li>
		<strong>An organization’s reputation can be ruined</strong> if the attacker edits the website content and includes malicious information or links to a porn website</li>
<li>
		The <strong>web server can be used to install malicious software on users who visit the compromised website</strong>. The malicious software downloaded onto the visitor’s computer can be a virus, Trojan or Botnet Software, etc.</li>
<li>
		<strong>Compromised user data may be used for fraudulent activities</strong> which may lead to business loss or lawsuits from the users who entrusted their details with the organization</li>
</ul>
<h2><a id="5" data-lasso-id="199681" href="#"></a>Web server attack tools</h2>
<p>Some of the common web server attack tools include;</p>
<ul>
<li>
		<strong>Metasploit</strong>– this is an open source tool for developing, testing and using exploit code. It can be used to discover vulnerabilities in web servers and write exploits that can be used to compromise the server.</li>
<li>
		<strong>MPack</strong>– this is a web exploitation tool. It was written in PHP and is backed by MySQL as the database engine. Once a web server has been compromised using MPack, all traffic to it is redirected to malicious download websites.</li>
<li>
		<strong>Zeus</strong>– this tool can be used to turn a compromised computer into a bot or zombie. A bot is a compromised computer which is used to perform internet-based attacks. A botnet is a collection of compromised computers. The botnet can then be used in a denial of service attack or sending spam mails.</li>
<li>
		<strong>Neosplit </strong>– this tool can be used to install programs, delete programs, replicating it, etc.</li>
</ul>


<h2><a id="6" data-lasso-id="199682" href="#"></a>How to avoid attacks on Web server</h2>
<p>An organization can adopt the following policy to protect itself against web server attacks.</p>
<ul>
<li>
		<strong>Patch management</strong>– this involves installing patches to help secure the server. A patch is an update that fixes a bug in the software. The patches can be applied to the operating system and the web server system.</li>
<li>
		<strong>Secure installation and configuration of the operating system</strong></li>
<li>
		<strong>Secure installation and configuration of the web server software</strong></li>
<li>
		<strong>Vulnerability scanning system</strong>– these include tools such as Snort, NMap, Scanner Access Now Easy (SANE) </li>
<li>
		<strong>Firewalls </strong>can be used to stop simple DoS attacks by blocking all traffic coming the identify source IP addresses of the attacker.</li>
<li>
		<strong>Antivirus </strong>software can be used to remove malicious software on the server</li>
<li>
		<strong>Disabling Remote Administration</strong></li>
<li>
		<strong>Default accounts and unused accounts must be removed</strong> from the system</li>
<li>
		<strong>Default ports  &amp; settings (like FTP at port  21) should be changed to custom port &amp; settings (FTP port at 5069)</strong></li>
</ul>
<h2><a id="7" data-lasso-id="199683" href="#"></a>Hacking Activity: Hack a WebServer</h2>
<p>In this practical scenario, we are going to look at the anatomy of a web server attack. We will assume we are targeting <a href="http://www.techpanda.org/" data-lasso-id="199684" rel="noopener">www.techpanda.org</a>. We are not actually going to hack into it as this is illegal. We will only use the domain for educational purposes.</p>
<h3>What we will need</h3>
<ul>
<li>
		A target <a href="http://www.techpanda.org/" data-lasso-id="199685" rel="noopener">www.techpanda.org</a></li>
<li>
		Bing search engine</li>
<li>
		SQL Injection Tools</li>
<li>
		PHP Shell, we will use dk shell <a href="https://sourceforge.net/projects/icfdkshell/" data-lasso-id="199686" rel="noopener">http://sourceforge.net/projects/icfdkshell/</a></li>
</ul>
<h3>Information gathering</h3>
<p>We will need to get the IP address of our target and find other websites that share the same IP address.</p>
<p>We will use an online tool to find the target’s IP address and other websites sharing the IP address</p>
<ul>
<li>
		Enter the URL <a href="https://www.yougetsignal.com/tools/web-sites-on-web-server/" data-lasso-id="199687" rel="noopener">https://www.yougetsignal.com/tools/web-sites-on-web-server/</a> in your web browser</li>
<li>
		Enter <a href="http://www.techpanda.org/" data-lasso-id="199688" rel="noopener">www.techpanda.org</a> as the target</li>
</ul>


<p style="margin-left: 18pt; text-align: center;">
	<img width="703" height="263" title="How to hack a Web Server" alt="How to hack a Web Server" src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check.png" class="lazyloaded" data-ll-status="loaded"><noscript><img width="703" height="263" title="How to hack a Web Server" alt="How to hack a Web Server" src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check.png"></noscript></p>
<ul>
<li>
		Click on Check button</li>
<li>
		You will get the following results</li>
</ul>
<p style="margin-left: 18pt; text-align: center;">
	<img width="712" height="673" title="How to hack a Web Server" alt="How to hack a Web Server" src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check1.png" class="lazyloaded" data-ll-status="loaded"><noscript><img width="712" height="673" title="How to hack a Web Server" alt="How to hack a Web Server" src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check1.png"></noscript></p>
<p><strong>Based on the above results, the IP address of the target is 69.195.124.112</strong></p>
<p>We also found out that there are 403 domains on the same web server.</p>
<p>Our next step is to scan the other websites for<a href="/sql.html" onclick="ga('send', 'event', 'internal_linking', 'How to Hack a Web Server', 'How to Hack a Web Server');" data-lasso-id="199689"> SQL </a>injection vulnerabilities. Note: if we can find a SQL vulnerable on the target, then we would directly exploit it without considering other websites.</p>
<ul>
<li>
		Enter the URL <a href="https://www.bing.com/" data-lasso-id="199690" rel="noopener">www.bing.com</a> into your web browser. This will only work with Bing so don’t use other search engines such as google or yahoo</li>
<li>
		Enter the following search query</li>
</ul>
<p>ip:69.195.124.112 .php?id=</p>
<p><strong>HERE,</strong></p>
<ul>
<li>
		“ip:69.195.124.112” limits the search to all the websites hosted on the web server with IP address 69.195.124.112</li>
<li>
		“.php?id=” search for URL GET variables used a parameters for SQL statements.</li>
</ul>
<p>You will get the following results</p>
<p style="text-align: center;">
	<img width="643" height="649" title="How to hack a Web Server" alt="How to hack a Web Server" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20643%20649'%3E%3C/svg%3E" data-lazy-src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check2.png"><noscript><img width="643" height="649" title="How to hack a Web Server" alt="How to hack a Web Server" src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check2.png"></noscript></p>
<p>As you can see from the above results, all the websites using GET variables as parameters for SQL injection have been listed.</p>
<p>The next logic step would be to scan the listed websites for SQL Injection vulnerabilities. You can do this using manual SQL injection or use tools listed in this article on SQL Injection.</p>
<h3>Uploading the PHP Shell</h3>
<p>We will not scan any of the websites listed as this is illegal. Let’s assume that we have managed to login into one of them. You will have to upload the PHP shell that you downloaded from <a href="https://sourceforge.net/projects/icfdkshell/" data-lasso-id="199691" rel="noopener">http://sourceforge.net/projects/icfdkshell/</a></p>
<ul>
<li>
		Open the URL where you uploaded the dk.php file.</li>
<li>
		You will get the following window</li>
</ul>
<p style="margin-left: 18pt; text-align: center;">
	<img width="842" height="323" title="How to hack a Web Server" alt="How to hack a Web Server" src="data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20842%20323'%3E%3C/svg%3E" data-lazy-src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check3.png"><noscript><img width="842" height="323" title="How to hack a Web Server" alt="How to hack a Web Server" src="https://raw.githubusercontent.com/dshubitidze/blog/main/assets/img/pexels/Reverse_ip_domain_check3.png"></noscript></p>
<ul>
<li>
		Clicking the Symlink URL will give you access to the files in the target domain.</li>
</ul>
<p>Once you have access to the files, you can get login credentials to the database and do whatever you want such as defacement, downloading data such as emails, etc.</p>
<h2>Summary</h2>
<ul>
<li>
		Web server stored valuable information and are accessible to the public domain. This makes them targets for attackers.</li>
<li>
		The commonly used web servers include Apache and Internet Information Service IIS</li>
<li>
		Attacks against web servers take advantage of the bugs and Misconfiguration in the operating system, web servers, and networks</li>
<li>
		Popular web server hacking tools include Neosploit, MPack, and ZeuS.</li>
<li>
		A good security policy can reduce the chances of been attacked</li>
</ul>


</div>
