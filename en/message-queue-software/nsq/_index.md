---
keywords: distributed message queue, message queue software, open source message broker, message queuing service, message queue system, best message queue, best message broker
title: NSQ | Most Popular Open Source Distributed Message Queue
description: NSQ is an open-source distributed message queue platform. It supports fault tolerance, high availability, and scale-out with reliable message delivery.
singlepageh1title: Go-based Open Source & Real-time Distributed Message Queue
singlepageh2title: NSQ is an open-source real-time distributed message queue with no single point of failure. It is a reliable message delivery service with high availability.
Shortdescriptionlistingpage: NSQ is easy to configure and deploy real-time distributed memory message queuing platform. It has a built-in management interface and supports high availability.
linktitle: NSQ
Imagetext: Free Message Queue Software
draft: false
weight: 5
layout: "single"
GithubLink: https://github.com/nsqio/nsq
HomePage_TitleText: NSQ is an open source distributed message queue platform

ListingPage_MenuImage_TitleText: NSQ is an open source distributed message queue software
ListingPage_MenuImage_AltText: NSQ is an open source distributed message queue software
ListingPage_Link_TitleText: NSQ is an open source distributed message queue software.

SinglePage_HeaderImage_TitleText: NSQ is an open source distributed message queue software
SinglePage_HeaderImage_AltText: NSQ is an open source distributed message queue software
SinglePage_MenuImage_TitleText: NSQ is an open source distributed message queue software
SinglePage_MenuImage_AltText: NSQ is an open source distributed message queue software

---

### **Overview**

NSQ is a realtime distributed messaging platform operatng at a scale. It handles huge number of messages every day, providing fault tolerance and high availability with a reliable messages delivery. It provides distributed and decentralized topologies without single points of failure. Operationally, NSQ best message queue is easy to install, configure and deploy. NSQ messages can be JSON, MsgPack, Protocol Buffers or anyother data format to achieve maximum flexibility. Official Go and Python client libraries are also available.

One of the design goal of NSQ message queue system is to bound the number of messages kept in memory. Topics, distinct stream of data and channels, logical grouping of streams or consumers subscribed to a given topic are the core primitives of NSQ. NSQ message queuing service is composed of 3 daemons: nsqd is the daemon that receives, buffers, and delivers messages to clients. nsqlookupd serves client requests to find the topics location and manages cluster metadata. It provides runtime consistent discovery service for consumers to find nsqd producers for a specific topic. nsqadmin is a web service UI for the cluster realtime administrative tasks of your NSQ cluster.