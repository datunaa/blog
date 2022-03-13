---
layout: post
title: ICE vs STUN vs TURN
feature-img: "assets/img/feature-img/big-pool.jpg"
thumbnail: "assets/img/feature-img/big-pool.jpg"
tags: [big pool, ICE, STUN, TURN ]
---

**This answer is for someone new to Webrtc**
before we dive into the difference between **STUN**(**Session Traversal Utilities** for **NAT**) and **TURN**(**Traversal Using relays** around **NAT**), we need to understand how two deceives/peers can communicate via **[NAT](https://en.wikipedia.org/wiki/Network_address_translation)**(**Network address translation**) and its different methods:

* **Full-cone NAT**, also known as one-to-one NAT, and less secure where anyone can connect to you and send data.
* **(Address)-restricted-cone NAT**, sender IP-address must match with one of your NAT table visitors addresses.
* **Port-restricted cone NAT**, like Address-restricted-cone NAT, but the restriction includes port numbers.
* **Symmetric NAT**, allow a full-pair match only, most secure but not recommended.

**STUN**:

* works with **full-cone NAT**,
* works with **(Address)-restricted-cone NAT**.
* works with **Port-restricted cone NAT**
* doesn't work with **Symmetric NAT**
* cheap to use and maintain.

**TURN**

* works with **Symmetric NAT**
* expansive to maintain
* is the server/channel that forwards/relays the data packets between devices/peers like a reverse proxy at layer 4
* expansive to use and maintain

**ICE(Interactive Connectivity Establishment)** is a protocol that lets two devices use an intermediary to exchange offers and answers even if the two devices are separated by **NAT**. it's a way of collecting information that describes the optimal path of connection between peers, and this information is put in an object called **ICE candidate**.
**ICE candidates** are objects consisting of the local-IP address, security &amp; routing protocols like reflexive addresses (**STUN**) and relayed addresses (**TURN**), supported formats, etc... and all ICE candidates/collected information are sent to the peer via **SDP**.
**SDP(Session Description Protocol)** is an important part of WebRTC.  it is a protocol or format as most people consider, used for negotiation between peers that describes ICE candidates, various audio and video codecs, network topologies, bandwidth, and other device information. the only question that remains is how do we send this SDP to the other peer? well, the right answer is up to you and we call it **SDP SIGNALING**.
**SIGNALLING**: refers to the signaling service or channel in the middle that can be anything **`(email, WhatsApp, postman, WebSockets, HTTP, pizza delivery guy).`** that will somehow manage to get the SDP information to the other peer.
{% include aligner.html images="pexels/stun-1.png" column=1 %}
in a nutshell, a **STUN** server is used to get an external network address, and **TURN** server is used to relay traffic if a direct (peer-to-peer) connection fails, a **TURN** server is a **STUN** server with additional built-in relaying functionality. whereas the **Signaling** server is used to let peers share service information to start the transmission of the peer-to-peer stream
{% include aligner.html images="pexels/stun-2.png" column=1 %}
other resources to help you understand webRTC, NAT, and networking:

* <a href="https://www.youtube.com/watch?v=XQ3T14SIlV4&amp;t=1075s&amp;ab_channel=NexGenT" rel="noreferrer">subnetting</a>
* <a href="https://www.youtube.com/watch?v=FTUV0t6JaDA&amp;t=170s&amp;ab_channel=PowerCertAnimatedVideos" rel="noreferrer">NAT and IPV4 &amp; IPV6</a>
* <a href="https://www.youtube.com/watch?v=FExZvpVvYxA&amp;ab_channel=HusseinNasser" rel="noreferrer">webRTC crash course</a>
* <a href="https://www.youtube.com/watch?v=4dLJmZOcWFc&amp;ab_channel=WebRTC.ventures" rel="noreferrer">STUN VS TRUN SERVERS</a>
* <a href="https://www.html5rocks.com/en/tutorials/webrtc/infrastructure/" rel="noreferrer">STUN, TURN, and signaling</a>
* <a href="https://www.html5rocks.com/en/tutorials/webrtc/basics/" rel="noreferrer">Quick start with webRTC</a>

    





TURN is a relay — both clients send data to the TURN server, which forwards it to the other client.

STUN is not a relay — the STUN server helps to "make the connection" between the clients (by discovering and exchanging their external host:port pairs),
after which they send data to each other directly. However, STUN doesn't work with all NAT/firewall setups, so TURN is used when STUN fails.
