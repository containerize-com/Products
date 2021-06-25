---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

## Install ownCloud On Ubuntu

First, ensure that all the depency packages of ownCloud are up to date before installing owncloud on ubuntu. To setup owncloud, first check PHP is available in the APT repository. Now please follow the instructions listed below:

    apt update && \
      apt upgrade -y

Create a helper script to simplify running occ commands and make the script executable:

    FILE="/usr/local/bin/occ"
    /bin/cat <<EOM >$FILE
    #! /bin/bash
    cd /var/www/owncloud
    sudo -E -u www-data /usr/bin/php /var/www/owncloud/occ "\$@"
    EOM

    chmod +x /usr/local/bin/occ

Now, download open source ownCloud on ubuntu:

cd /var/www/
wget https://download.owncloud.org/community/owncloud-10.7.0.tar.bz2 && \
tar -xjf owncloud-10.7.0.tar.bz2 && \
chown -R www-data. owncloud

Next, install ownCloud with:

    occ maintenance:install \
        --database "mysql" \
        --database-name "owncloud" \
        --database-user "owncloud" \
        --database-pass "password" \
        --admin-user "admin" \
        --admin-pass "admin"

Now configure ownCloud’s private cloud storage solution trusted domains:

    myip=$(hostname -I|cut -f1 -d ' ')
    occ config:system:set trusted_domains 1 --value="$myip"

Finally, set your background job mode to cron

    occ background:cron
    echo "*/15  *  *  *  * /var/www/owncloud/occ system:cron" \
      > /var/spool/cron/crontabs/www-data
    chown www-data.crontab /var/spool/cron/crontabs/www-data
    chmod 0600 /var/spool/cron/crontabs/www-data

Make sure the owncloud permissions are correct

    cd /var/www/
    chown -R www-data. owncloud

Now access the ownCloud web panel directory on your favourite web browser. Change localhost to your server IP address or domain name.

    http://localhost/owncloud/

Congratulations! You have now set up the ownCloud software. Enjoy!
