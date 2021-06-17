---
title: Installation Guide
onpagelink: installation
weight: 3

---
### Installation

Haraka requires Node.js to run you can install Haraka with npm:
```
npm install -g haraka
```

After installation, use the `haraka` binary to set up the service. First, create the service:

```
haraka -i /path/to/haraka_test
```

That creates the directory `haraka_test` with `config` and `plugin` directories within. It also sets the host name used by Haraka to the output of hostname.

If `hostname` is not correct, edit `config/host_list`. For example, to receive mail addressed to `user@domain.com`, add `domain.com` to the `config/host_list` file.

Finally, start Haraka using root permissions:

```
haraka -c /path/to/haraka_test
```

And it'll run.


### Explore

You may find the following links relevant:
- [Top 5 Open Source Mail Transfer Agents for Linux in 2020](https://blog.containerize.com/2020/10/02/top-5-open-source-mail-transfer-agents-for-linux-in-2020/)
- [Top 5 Open Source Newsletter Software in 2021](https://blog.containerize.com/2021/04/23/top-5-open-source-newsletter-software-in-2021/)
- [Postfix Mail Server](https://products.containerize.com/transactional-email/postfix/)
- [hMailServer](https://products.containerize.com/transactional-email/hmailserver/)