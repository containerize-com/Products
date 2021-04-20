---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once pre-requisites are installed, run the following command to clone the source code:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected is-hovered rich-text" contenteditable="true" data-block="7dfdf536-e15b-4ec6-84fb-479d4638c2b0" data-title="Preformatted" data-type="core/preformatted" id="block-7dfdf536-e15b-4ec6-84fb-479d4638c2b0" tabindex="0">```
git clone https://github.com/openmrs/openmrs-core.git
```
```

Then, run the following commands:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text" contenteditable="true" data-block="a3d087d5-6baf-475a-ba4e-f51ffd9515ea" data-title="Preformatted" data-type="core/preformatted" id="block-a3d087d5-6baf-475a-ba4e-f51ffd9515ea" spellcheck="false" tabindex="0">```
cd openmrs-core<br data-rich-text-line-break="true"></br>mvn clean package
```
```

This will generate the OpenMRS application in `webapp/target/openmrs.war` which you will have to deploy into an application server such as [tomcat](https://tomcat.apache.org/).

Now, you can simply deploy the `openmrs.war` into the application server jetty by running the following commands:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text" contenteditable="true" data-block="38e6aeeb-9bd4-4cb9-9fa3-d8dec8084d19" data-title="Preformatted" data-type="core/preformatted" id="block-38e6aeeb-9bd4-4cb9-9fa3-d8dec8084d19" spellcheck="false" tabindex="0">```
cd openmrs-core/webapp<br data-rich-text-line-break="true"></br>mvn jetty:run
```
```

Finally, you can access this health management information system at `localhost:8080/openmrs`.

#### **Explore**

<div class="entry-content">You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
- [How Online Healthcare Software Empowers Healthcare Industry](https://blog.containerize.com/2021/02/12/how-online-healthcare-software-empowers-healthcare-industry/)
- [How To Set Up eHealth System Hospitalrun On Localhost](https://blog.containerize.com/2021/02/19/how-to-set-up-ehealth-system-hospitalrun-on-localhost/)
- [Features Exploration Of Medical Health Solution OpenEMR](https://blog.containerize.com/2021/02/26/features-exploration-of-medical-health-solution-openemr/)
 
 </div>