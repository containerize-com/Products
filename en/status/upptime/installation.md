---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Creating repository from the Upptime template

Follow the below steps for creating repository from the template.

- Open the Upptime GitHub repository by visiting: <https://github.com/upptime/upptime>
- Click on the "Use this template" button on the top-right.
- Enter a name for your new repository and check "Include all branches".
- Click on "Create repository from template"
 
#### Enable GitHub Pages

Enable GitHub pages for generating static website. Follow the below steps to newly created repository.

- Navigate to repository settings page.
- Scroll to the "GitHub Pages" settings.
- Under "Source", change "None" to gh-pages.
- In the folder dropdown, select /(root).
- Skip the "Theme Chooser" option.
- Click on "Save"
 
#### Update Configuration File

The ".upptimerc.yml" file is used as the central configuration to add endpoints/websites for monitoring and configure status website. Configuration file should look like this one.

 ```
 
owner: masoodanwer # GitHub username
repo: upptime-test-repo # GitHub repository name
sites: 
  - name: Google
    url: https://www.google.com
assignees: 
  - MasoodAnwer
status-website: 
  cname: /repo
  name: My Status Website

```
