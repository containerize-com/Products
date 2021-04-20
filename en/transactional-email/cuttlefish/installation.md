---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

We use Vagrant and Ansible to automatically set up a fresh server with everything you need to run Cuttlefish. It's a fairly complicated affair as Cuttlefish does have quite a few moving parts but all of this is with the purpose of making it easier for the developer sending mail.

These instructions are specifically for installing the server at https://cuttlefish.oaf.org.au.

#### To install to a local test virtual machine

1. Create a file ~/.cuttlefish\_ansible\_vault\_pass.txt which contains the password for encrypting the secret values used in the deploy. The encrypted variables are at provisioning/roles/cuttlefish-app/vars/main.yml.
2. Download base box and build virtual machine with everything needed for Cuttlefish. This will take a while (at least 30 mins or so) ```
  vagrant up
  ```
3. Deploy the application. As this is the first deploy it will take quite a while (5 mins or so). Further deploys will be much quicker. We're using the --set-before local\_deploy=true flag to deploy to your local test virtual machine instead of production. ```
  bundle exec cap --set-before local_deploy=true deploy:setup deploy:cold foreman:export foreman:start
  ```
4. Add to your local /etc/hosts file ```
  127.0.0.1       cuttlefish.oaf.org.au
  ```
5. Point your web browser at https://cuttlefish.oaf.org.au:8443/
 