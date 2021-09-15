---
title: System Requirements
onpagelink: requirements
weight: 1

---

### System Requirements
-------------------

concrete5 is written primarily in PHP. Additionally, some PHP extensions which provide extra functionality are needed. The version of the PHP interpreter and the PHP extensions needed depends on the version of concrete5 in use. Below you will find details for both supported major versions of concrete5.

### concrete5 Version 8

Version 8 is the current major release of concrete5. The latest released version of this series is considered to be the most secure and stable version.

### PHP Requirements

PHP-7.3 works with 8.5+   
 PHP-7.4 works with future v9.0 release

### Choosing a PHP version

If a version is marked as "Works with concrete5", that means we would expect concrete5 to run acceptably in that environment. If it is marked as "Recommended for concrete5", that means it is a version that we would choose for our production environments, and it is the version that what we are testing with.

### PHP Extensions

concrete5 version 8.x requires the following PHP extensions:

- MySQL (with PDO extensions)
- DOM
- SimpleXML
- iconv
- GD Library with Freetype
- Fileinfo
- Mbstring
- CURL
- Mcrypt
- ZipArchive (For automatic updates and community functionality)
 
### PHP Configuration

concrete5 version 8.x requires the following configuration:

- PHP Safe Mode Off
- PHP Memory Limit at least 64 MB (more might be required for the processing and handling of large image files).
- MySQL 5.1.5 or Higher, or MariaDB, with `utf8mb4` support.
- MySQL InnoDB Table Support
 
### concrete5 Version 7

*Note: it is strongly recommended that you upgrade your concrete5 5.7.x sites to version 8 or greater.*

### PHP Requirements

PHP-7.3 N/A   
 7.4 N/A No

### Choosing a PHP version

If a version is marked as "Works with concrete5", that means we would expect concrete5 to run acceptably in that environment. If it is marked as "Recommended for concrete5", that means it is a version that we would choose for our production environments, and it is the version that what we are testing with.

### PHP Extensions

concrete5 5.7.x requires the following PHP extensions:

- MySQL (with PDO extensions)
- DOM
- SimpleXML
- GD Library with Freetype
- CURL
- Mcrypt
- ZipArchive (For automatic updates and community functionality)
 
### PHP Configuration

concrete5 version 5.7.x requires the following configuration:

- PHP Safe Mode Off
- PHP Memory Limit at least 64 MB (more might be required for the processing and handling of large image files.)
- MySQL 5.1.5 or Higher, or MariaDB
- MySQL InnoDB Table Support
 
### Web Server

concrete5 supports both Apache and Nginx web servers, and has been made to work with IIS in the past. Official support is for Apache and Nginx only.

### Database

MySQL (5.7 or higher) or MariaDB both work. If possible, set the table `row_format` to `dynamic` to avoid problems with large forms.
