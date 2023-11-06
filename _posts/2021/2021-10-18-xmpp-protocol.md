---
layout: post
title:  "xmpp protocol"
date:   2021-10-18 11:54:49 +0530
categories: xmpp realtime-communication
permalink: '/post/xmpp-protocol'
---

xmpp stands for eXtensible Messaging and Presence Protocol. Developed by and originally called jabber, xmpp is used for instant messaging including audio and video calls. Data is transmitted as xml file when using xmpp.

To connect through xmpp a person John, will have to have an jabber id like `john@abc.org`. Using this id he can connect with Jack having id `jack@xyz.org`. Just like email the domain name here doesn't matter. If you have a valid id with valid server than you can chat directly with anyone.

Now xmpp has two main component - server and client. Server's provide basic messaging and xml routing features. [These](https://xmpp.org/software/servers/) are some sites that provide jabber server software that can be used to run xmpp service. There are sites like `jabber.at` and `xmpp.js` where upon registration one can get jabber id like `john@abc.org` from the respective servers.

Getting jabber id for yourself and your friend is the first step. Next to communicate between you two you need an interface or a client.[Here](https://xmpp.org/software/clients/) are some list of jabber client apps in which you can connect with anyone having a jabber id. There is also the site conversejs.org which provides xmpp chat client on browser. 