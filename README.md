# Magento2 Deploy Scripts

Deploy scripts are based on the superb work of [@fbrnc](https://twitter.com/fbrnc) and AOE (https://github.com/AOEpeople/magento-deployscripts) for Magento 1

## How it works

1) Whole magento project is packaged into a build archive (project.tar.gz)
```
vendor/bin/build.sh -f project.tar.gz -b 3
```

2) Generated build is copied to a central storage server
3) Jenkins copies/pulls deploy.sh to remote server
4) deploy.sh is executed on remote server and initiates install.sh
```
magento2-deployscripts/deploy.sh -r /tmp/artifacts/project.tar.gz -e devbox -d -t /var/www/project/devbox/
```
5) Jenkins triggers cleanup script on remote server

# Defining settings with zettr.phar

Define configuration in config/settings.csv regarding the
zettr documentation

 - Environment Settings
 - Database updates
 - XmlFile configuration