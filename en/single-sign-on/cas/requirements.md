---
title: System Requirements
onpagelink: requirements
weight: 1

---

System Requirements
-------------------

- JDK 11
- Apache Tomcat
- Docker (optional)
 
<div class="col-lg-12">Features
--------

 </div><div class="col-lg-12">- OAuth v2 Protocol
- OpenID &amp; OpenID Connect Protocol
- Password Management
- Various Deployment Options
- Multifactor authentication
- Multilingual
- Sign-in / Sign-out
- Many Authentication Mechanisms (e.g. JAAS, LDAP, RDBMS)
- WS-Federation Passive Requestor Protocol
- Easy to Set-Up
- Integrations With Third Parties
- Many Authorization Mechanisms (e.g. ABAC, Time/Date, REST )
- UI To Manage Logs
- UI To Manage Monitoring And Stats
- Delegated Authentication To Facebook, Twitter And More
 
 </div><div class="col-lg-12">Installation Instructions
-------------------------

Run the following command to clone the repo:

 ```
<pre class="wp-block-preformatted">```bash
git clone <span id="cloak690e1a4907070237f8ea4f4a4902942a">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak690e1a4907070237f8ea4f4a4902942a').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy690e1a4907070237f8ea4f4a4902942a='g&#105;t'+'&#64;';addy690e1a4907070237f8ea4f4a4902942a=addy690e1a4907070237f8ea4f4a4902942a+'g&#105;th&#117;b'+'&#46;'+'c&#111;m';var addy_text690e1a4907070237f8ea4f4a4902942a='g&#105;t'+'&#64;'+'g&#105;th&#117;b'+'&#46;'+'c&#111;m';document.getElementById('cloak690e1a4907070237f8ea4f4a4902942a').innerHTML+='<a '+path+'\''+prefix+':'+addy690e1a4907070237f8ea4f4a4902942a+'\'>'+addy_text690e1a4907070237f8ea4f4a4902942a+'<\/a>';</script>:apereo/cas.git cas-server
```
```

After successful clone, run the following command:

 ```
<pre class="wp-block-preformatted">```bash
cd cas-server
```
```

 ```
<pre class="wp-block-preformatted">```bash
git checkout master
```
```

Now, build the codebase via the following command:

 ```
<pre class="wp-block-preformatted">```bash
./gradlew build install --parallel -x test -x javadoc -x check
```
```

You can use `-x <task>` to entirely skip/ignore a phase in the build. (i.e. `-x test`, `-x check`).

If you have no need to let Gradle resolve/update dependencies and new module versions for you, you can take advantage of the `--offline` flag when you build which tends to make the build go a lot faster.

Using the Gradle daemon also is a big help. It should be enabled by default.

Enabling Gradle’s build cache via `--build-cache` can also significantly improve build times.

If you are using Windows, you may find `-DskipNpmLint=true` needed for the build due to line ending difference between OS

For configuring SSL, the `thekeystore` file must include the SSL private/public keys that are issued for your CAS server domain. You will need to use the `keytool` command of the JDK to create the keystore and the certificate. The following commands may serve as an example:

 ```
<pre class="wp-block-preformatted">```bash
keytool -genkey -alias cas -keyalg RSA -validity 999 -keystore /etc/cas/thekeystore -ext san=dns:$REPLACE_WITH_FULL_MACHINE_NAME
```
```

In your `/etc/hosts` file (on Windows: `C:\Windows\System32\Drivers\etc\hosts`), you may also need to add the following entry:

 ```
<pre class="wp-block-preformatted">```bash
127.0.0.1 mymachine.domain.edu
```
```

The certificate exported out of your keystore needs to also be imported into the Java platform’s global keystore:

 ```
<pre class="wp-block-preformatted">```bash
keytool -export -file /etc/cas/config/cas.crt -keystore /etc/cas/thekeystore -alias cas
sudo keytool -import -file /etc/cas/config/cas.crt -alias cas -keystore $JAVA_HOME/jre/lib/security/cacerts
```
```

where `JAVA_HOME` is where you have the JDK installed (i.e `/Library/Java/JavaVirtualMachines/jdk[version].jdk/Contents/Home`).

Execute the following commands to deploy:

 ```
<pre class="wp-block-preformatted">```bash
cd webapp/cas-server-webapp-tomcat
../../gradlew build bootRun --parallel --offline --configure-on-demand --build-cache --stacktrace
```
```

By default CAS will be available at `<a href="https://href.li/?https://mymachine.domain.edu:8443/cas" rel="nofollow">https://mymachine.domain.edu:8443/cas</a>`

 </div>### Running in Docker

For Docker, Docker image is located at [Docker Hub](https://href.li/?https://hub.docker.com/r/apereo/cas/). Run the following command to pull down the Docker Image:

 ```
<pre class="wp-block-preformatted">```bash
docker pull apereo/cas:v[A.B.C]
```
```

where `[A.B.C]` represents the image tag that is mapped to the CAS server version.

#### **Explore**

You may find the following links relevant:

- **[Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)**
 