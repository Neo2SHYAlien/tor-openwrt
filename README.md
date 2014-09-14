# Implementation of WiFi hotspot and middle relay with anonymity network #
======================================================================

### Using Tor network on TP-LINK WDR4300 with OpenWRT
Run Chen, (run.chen@mail.polimi.it) <br/>
Jorge Díez de la Fuente, (jorge.diez.delafuente@alumnos.upm.es)

Report for the master course of Embedded Systems <br/>
Reviser: PhD. Federico Terraneo (federico.terraneo@polimi.it)

Received: July, 2014

## Abstract ##

Increasing network users and the continuing growth of information technology have made people to pay attention in security issues. Our project focuses on providing more privacy and protection to small and medium WiFi hotspot provider while they’re providing internet and to users as well they’re surfing internet. <br/>
As you know, WiFi hotspot provide us a free internet connection in specific areas around the world, but in most cases is lack of sufficient privacy for users. We implemented a WiFi hotspot with tor network, and provide users a higher level of privacy and anonymity. On the other hand, this implementation protects the hotspot provider from any illegality which is committed in its network. <br/>
Finally we will present our conclusion based on test results, we will also discuss our opinion about this implementation, pros and cons. We also comment some security issues about this implementation, we describe those problem and propose a solution.

## 1. Introducction ##

The purpose of this project is implementing a middle node and wifi hotspot through tor network in a commercial router and evaluate its performance. First we will make a brief introduction of each part of the project. We start explaining what is tor, different types of tor relay and why we want to implement a wifi hotspot with tor.

### 1.1. Tor network ###

> Tor (acronym for The Onion Router) is free software for enabling online anonymity and resisting censorship. Tor directs Internet traffic through a free, worldwide, volunteer network consisting of more than five thousand relays to conceal a user's location or usage from anyone conducting network surveillance or traffic analysis. Using Tor makes it more difficult for Internet activity to be traced back to the user: this includes "visits to Web sites, online posts, instant messages, and other communication forms". Tor's use is intended to protect the personal privacy of users, as well as their freedom and ability to conduct confidential communication by keeping their Internet activities from being monitored.

Wikipedia.  [TOR anonymity network](http://en.wikipedia.org/wiki/Tor_(anonymity_network))

Tor network is consist of Entry node, Middle node and Exit node. We are focussing on Middle node in our project.

![alt text](https://github.com/SuperBuker/tor-openwrt/raw/master/doc/img/tornet.png "Tor Network")

### 1.2 Middle relays ###

> Middle relays which receive traffic and pass it to another relay. Middle relays increase robustness and accelerate speed of the Tor network without making the owner of the relay look like the source of the traffic. Middle relays advertise their presence to the rest of the Tor network, so that any Tor user can connect to them. Even if a malicious user employs the Tor network to do something illegal, the IP address of a middle relay will not show up as the source of the traffic. That means a middle relay is generally safe to run in your home, in conjunction with other services, or on a computer with your personal files.

TOR project. [TOR Relay Debian](https: //www.torproject.org/docs/tor-relay-debian.html.en/)

### 1.3 WIFI hotspot through TOR ###

We want to share our wifi access point. When the traffic is routing through tor network, we can obtain a manner to provide security to the WIFI hotspot-owner since the traffic of people who connected to our system is spreading through Tor and avoiding by someone misuses our network.
The main advantages are:
Traffic is routed encryted through the tor-network and when the packet reaches "outside" there is no way to know from where come from.
Users connected to hotspot don't know anything about router network structure(ip, lan, .., etc. it provides more privacy for owner.
