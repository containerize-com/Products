---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing on Ubuntu

Install and configure the necessary dependencies packages.

 ```

sudo apt-get update
sudo apt-get install -y curl openssh-server ca-certificates tzdata

```

Run command to add GitLab repository.

 ```
curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash
```

Install the GitLab package. Replace example domain with your real domain.

 ```
sudo EXTERNAL_URL="https://gitlab.example.com" apt-get install gitlab-ee
```

Open your browser and visit site. It will redirect to the password reset screen. Set password and you will be redirected to login screen where you can signin with root user.

