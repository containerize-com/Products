---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install CovidVolunteers on Ubuntu

CovidVolunteers virtual volunteering service is easy to setup and get started. To get started with covid volunteer services on Ubuntu quickly, configure and setup Rails development environment with the necessary dependencies packages. Install dependencies:

    bundle install
    yarn install

Now first clone the covid-volunteers repository in ~/covid-volunteers folder:

    git clone https://github.com/helpwithcovid/covid-volunteers.git covid-volunteers

Setup the database and seed data:

    rails db:setup

Now, try running the specs tests:

    bundle exec rails spec

Make sure rubocop is happy by running

    bundle exec rubocop

The following environment variables can be set:

    ADMINS
    EXCEPTION_NOTIFIERS	
    EMAIL_ADDRESS

Start rails server available only on localhost:

    rails server

You should now be able to connect to covid volunteer opportunities app on http://localhost:3000 to view app.

Congratulations! You have successfully installed covid volunteer organization. Enjoy!

Explore
-------

In this article we discussed about CovidVolunteers open source virtual volunteer opportunities software. To learn about other open source community service opportunities software, please visit following page:

*   [Best Open Source Discussion Forum](https://products.containerize.com/discussion-forum)