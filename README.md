# Docker-compose HTML + PHP (nginx or varnish) localhost

This repo is for setting a webserver (Nginx or Varnish + PHP) in localhost.

## Files

Folder structure:

```
\config\database\
\config\nginx\
\config\nginx\conf.d\
\config\varnish\
\web\
\
```

## Steps 

**Database**

You only need to create or be sure that there is an empty folder called "database" into config folder.


**ENV file**

This is the file for setting your site.
- PROJECT_NAME is the folder where you will clone the repo.
- DOMAIN_NAME is the name you will need to write in the /etc/hosts file. Like www.seocrawler.test

**Web Folder**

In this folder you will drop your html files.

## Webserver configuration

The only thing you will need to update / review is the "website.conf" file in:
```
\config\nginx\conf.d\website.conf
```
Just to update:
- The server_name for the name you put in DOMAIN_IN
- Let listenning port 80 if you execute "nginx-local-yml",
- Or let listening port 8080 if you execute "varnish-nginx-local.yml".

## Docker compose

You can launch the project using (nginx local, for example):

```
docker-compose -f nginx-local.yml up -d
```
In your terminal.

NOTE:

It helps create an entry in your /etc/hosts file: (in the example)
```
127.0.0.1   www.seocrawler.test
```