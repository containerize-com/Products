---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Run the following command to clone the repo:

 ```
<pre class="wp-block-preformatted">```bash
git clone <span id="cloak8449dd627f223244e12c257807790bde">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak8449dd627f223244e12c257807790bde').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy8449dd627f223244e12c257807790bde='g&#105;t'+'&#64;';addy8449dd627f223244e12c257807790bde=addy8449dd627f223244e12c257807790bde+'g&#105;th&#117;b'+'&#46;'+'c&#111;m';var addy_text8449dd627f223244e12c257807790bde='g&#105;t'+'&#64;'+'g&#105;th&#117;b'+'&#46;'+'c&#111;m';document.getElementById('cloak8449dd627f223244e12c257807790bde').innerHTML+='<a '+path+'\''+prefix+':'+addy8449dd627f223244e12c257807790bde+'\'>'+addy_text8449dd627f223244e12c257807790bde+'<\/a>';</script>:apereo/cas.git cas-server
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