---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Coderwall on Heroku

Coderwall collaborative learning platform is easy to setup and get started. To get started with coderwall web developer forum on heroku quickly, configure and setup Rails development environment with the necessary dependencies packages. Now first clone the coderwall programmer community repository in ~/coderwall folder:

    git clone https://github.com/coderwall/coderwall-next.git coderwall
    cd coderwall

Now, run the bundler in project directory:

    bundle install --without production

Create the database and run migrations:

    rake db:create db:migrate

Create environment variables file:

    cp .env.sample .env

Kick up a server with foreman(or heroku local) running at localhost:5000

    bundle exec foreman start

The following environment variables can be set:

		GITHUB_ADMIN_USER
		GITHUB_ADMIN_USER_PASSWORD
		GITHUB_REDIRECT_URL
		GITHUB_CLIENT_ID
		GITHUB_SECRET
		STRIPE_PUBLISHABLE_KEY
		STRIPE_SECRET_KEY

Congratulations! You have successfully installed coderwall web developer community tool. Enjoy!

Explore
-------

In this article we discussed about coderwall open source programmer community software. To learn about other open source web developer forum softwares, please visit following page:

*   [Best Open Source Community Forums](https://products.containerize.com/discussion-forum)