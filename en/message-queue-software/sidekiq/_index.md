---
keywords: developer community, collaborative learning platform, web developer forum, programmer community, web developer community, latest programming languages
title: Sidekiq | Simple and efficient background processing framework
description: Sidekiq is a free, simple to integrate and efficient software to handle many jobs at the same time in the same process with multiple threads.
singlepageh1title: Ruby based simple and efficient background processing tool.
singlepageh2title: Sidekiq is a ruby based fully featured, high performance and simple to integrate with any Rails application fastest background jobs processing system.
Shortdescriptionlistingpage: Sidekiq is a simple to integrate, fully featured and very high performance fastest background jobs processing system. It handles many jobs at the same time in the same process.
linktitle: Sidekiq
Imagetext: Free Message Queue Software
draft: false
weight: 7
layout: "single"
GithubLink: https://github.com/mperham/sidekiq/
HomePage_TitleText: Simple and efficient background processing framework

ListingPage_MenuImage_TitleText: 
ListingPage_MenuImage_AltText: Ruby based Simple and efficient background processing system.
ListingPage_Link_TitleText: Sidekiq is a simple, fully featured and fastest background job processing system.

SinglePage_HeaderImage_TitleText: Sidekiq is a fully featured background jobs processing framework
SinglePage_HeaderImage_AltText: Sidekiq is a fully featured background jobs processing framework
SinglePage_MenuImage_TitleText: Sidekiq is a fully featured background jobs processing framework
SinglePage_MenuImage_AltText: Sidekiq is a fully featured background jobs processing framework

---

Sidekiq is a free, simple to integrate and efficient software to handle many jobs at the same time in the same process with multiple threads. It works and integrates tightly with Rails to make background jobs processing dead simple. Sidekiq is a full featured background jobs processing framework for Ruby language. It integrates with any modern Rails application as simple as possible and with much higher performance than other existing  message queue software.

Sidekiq is a framework to scale your applications by performing work in the background . This requires following three parts for background processings:

1. The Sidekiq client runs in any Ruby process of a puma or passenger application server process and allows you to create jobs for processing later.
2. Redis provides and helps in data storage for Sidekiq. It stores all the jobs data along with runtime and historical data to power Sidekiq's Web UI.
3. Each Sidekiq server process pulls jobs from the queue in Redis and processes them later.