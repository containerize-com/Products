---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Firstly, download the source code from this [link](https://us13.mailchimp.com/mctx/clicks?url=https%3A%2F%2Fhospitalrun.fra1.cdn.digitaloceanspaces.com%2Fdeployments%2Fhr-1.0.0-beta-generic.zip&h=3e79da04f5c6cd968d616537e74f30eef38c16590dc0cbc1945ec8ad214de9c0&v=1&xid=b329e96801&uid=57968001&pool=contact_facing&subject=HospitalRun+1.0+Beta%3A+deploy+instruction).

After that, run the following command:

 ```
<pre data-title="Preformatted">```
cd generic<br></br>cd server
``````

```
```

Then, change password on row 8,9 of `*conf/initcouch.sh*` and password on row 7 of *config-demo.js*.

Now, run the following command:

 ```
<pre data-title="Preformatted">```
docker-compose build && docker-compose up
```
```

Finally, access the patient record system in the browser at [*http://youripaddress:80*](https://us13.mailchimp.com/mctx/clicks?url=http%3A%2F%2Flocalhost&h=08bcb31adb6e8835e1e2cfb13c37d71f71b0135651705d415fc11e9a76e618b2&v=1&xid=b329e96801&uid=57968001&pool=contact_facing&subject=HospitalRun+1.0+Beta%3A+deploy+instruction) .

#### **Explore**

<div class="entry-content">You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
- [How Online Healthcare Software Empowers Healthcare Industry](https://blog.containerize.com/2021/02/12/how-online-healthcare-software-empowers-healthcare-industry/)
- [How To Set Up eHealth System Hospitalrun On Localhost](https://blog.containerize.com/2021/02/19/how-to-set-up-ehealth-system-hospitalrun-on-localhost/)
- [Features Exploration Of Medical Health Solution OpenEMR](https://blog.containerize.com/2021/02/26/features-exploration-of-medical-health-solution-openemr/)
 
 </div>