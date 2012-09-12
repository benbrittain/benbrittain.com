---
title: A Modest Proposal and Implementation of a Peer-To-Peer data channel using webRTC
author: Ben Brittain
date: August 21, 2012
---

WebRTC is a promising new standard for the web. The goal of WebRTC is to enable a whole host of applications such video chat, online games, and file sharing through a peer to peer connection. This is going to change the web as we know it. WebSockets, a protocol that allows fast communication between a browser and server, has resulted in many cool apps & websites. However, client-server communication has always been available, alebiet in much less sophisticated ways. WebRTC is going to be comletely new. A native way to communicate peer-to-peer between a large (or small) number of peers without any plugins is going to make web apps even more like native applications.

For the last couple of weeks, [Dennis Martensson](http://dennis.is) and I have been working on a library that aims to do for WebRTC what Socket.io did for WebSockets. Honestly, WebRTC is a pretty dense and complex protocol. There is a lot of stuff that the average developer really doesn't want to deal with when attempting to implement a peer-to-peer connection. You need to know what STUN servers are, how to send ICE candidates, ROAP vs JSEP, etc... etc... The goal of our webRTC.io library is to simplify what you need for a basic peer-to-peer web app. This has been great fun, and we've gotten some good feedback from developers. However, the  WebRTC specification is still missing the coolest part... <b> the data channel </b>.  

The data channol is the most awesome part of the webRTC specification, and the main developers don't even have a deadline for when it is supposed to have even basic functionality! Peer-to-peer anything! Dennis and I struck forth on our own. If we weren't given a data channel, we were gonna make a data channel!

We tried injecting data into the sound track and the video track to no avail. At long last, we stumbled upon the solution. We could send data through the webcam. Sure, the rate of data transfer would be paltry in comparison to well... practically anything, but it mattered not! With a little effort, we used our webRTC.io library and built the first peer-to-peer data channel using webRTC!

we have a demo here: LINK HERE

The best part about our implementation of the p2p data channel is that it requires human interaction! No longer are you a slave to your machine; You control what gets sent! The general steps are as follows:

1. You generate a QR code which contains some JSON with a unique id, an Ack Response, and a body field. It also has some error checking built in.

2. You take a picture. I'm sure the final version of the protocol will recommend a smartphone for fast turn around time.

3. Hold the picture up to your webcam, In our demo application, a red line should appear when your side has read the data. this does not mean the other peer has gotten the data! The QR code library is extremelly finicky. 

4. Continue holding the smartphone up to the webcam till the message you sent turns green. This could take a while depending who/what is on the other side of the connection. This means that you have received a new message which contains a succesful Acknowledgment. 

5. repeat!

Obviously this protocol needs a little work, but we have faith that the webRTC specification creators and implementors will take our suggestions into account. 


addendum: 
Title reference: http://en.wikipedia.org/wiki/A_Modest_Proposal
We love where webRTC is going, and we'd like to thank the developers of it. We just find it hilarious that we can send 30+fps video streams but not simple text.

