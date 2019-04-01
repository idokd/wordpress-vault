# wordpress-vault
Wordpress related scripts and configuration for hardening and protecting wordpress server

# Wordpress specific apache configuration file

just include the file in your apache config

Include wordpress-vault-apache.conf

or add it to the conf.d folder


# Wordpress Hardening permissions, depending on your apache user
 
 Expected linux file permissions
 
 Folders - 755
 
 Files - 644
 
 Use:
 
   find /path/to/your/wordpress/install/ -type d -exec chmod 755 {} \; 
   
   find /path/to/your/wordpress/install/ -type f -exec chmod 644 {} \;

# Disable File Editing on wp-config.php - dashboard

Disable Editing in Dashboard

define('DISALLOW_FILE_EDIT', true);

# Disable direct access to any of the following files (add if necessary any additonal files)

wp-cron.php is disabled, but you should run a cronjob running this script every 1min (or so...)

* * * * * php /path/to/your/wordpress/install/wp-cron.php
