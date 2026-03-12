---
tags:
  - area/databases
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/javascript
  - topic/networking
---

# Nginx

**Update default**

sudo nano /etc/nginx/sites-enabled/default

Add - proxy_set_header Host $http_host;

sudo nginx -t

sudo systemctl reload nginx

sudo tail -f /var/log/nginx/access.log

sudo tail -f /var/log/nginx/error.logs

Redis
systemctl restart spiped-redis-client-gra.service spiped-redis-client-sbg.service

**502 certificate issue:**

Change:
ssl_certificate     lg-infra-txai-app.crt;
ssl_certificate_key lg-infra-txai-app.key;

ssl_certificate     lg-infra-app.crt;
ssl_certificate_key lg-infra-app.key;

Bigger header

**spec.live not working**

etc/nginx/sites-enabled/

    location = /v5 {
        alias /usr/share/nginx/html/;
        try_files /spec.html =404;
    }

alias /usr/share/nginx/html/;

capgemini

Builder
urn:builder:capgemini:[capgemini.app.logicalglue.net](http://capgemini.app.logicalglue.net)

urn:admin:capgemini:[capgemini.app.logicalglue.net](http://capgemini.app.logicalglue.net)
urn:lgadmin:capgemini:[capgemini.app.logicalglue.net](http://capgemini.app.logicalglue.net)
urn:analyst:capgemini:[capgemini.app.logicalglue.net](http://capgemini.app.logicalglue.net)
urn:consumer:capgemini:[capgemini.app.logicalglue.net](http://capgemini.app.logicalglue.net)

psql -d app-cwb -h db-cwb-p.cavfqotprjty.ca-central-1.rds.amazonaws.com -U app-cwb

<redacted>

New Users:
- User list removed from this note. Keep personal data in the source system or a private access-controlled document.

 Builder         |     376
 Builder         |     377
 Builder         |     378
 Builder         |     379
 Builder         |     380
 Builder         |     381
 Builder         |     382
 Builder         |     383
 Builder         |     384

 381 | rukmani.srikanth@capgemini.com                  | Srikanth Rukmani                   | capgemini    | t
 379 | vijaykarthikeyan.s@capgemini.com                | S, Vijay Karthikeyan               | capgemini    | t
 380 | sneha.are@capgemini.com                         | Are, Sneha                         | capgemini    | t
 383 | gokul.mahajan@capgemini.com                     | Gokul, Mahajan                     | capgemini    | t
 385 | sankarasubramanian.ramakrishnan@capgemini.com   | Ramakrishnan, Sankarasubramanian   | capgemini    | t
 386 | sarang.bondre@capgemini.com                     | Sarang Bondre                      | capgemini    | t
 387 | ketan.a.varia@capgemini.com                     | Ketan Varia                        | capgemini    | t
 384 | yashwanth-kumar-reddy.konkala@capgemini.com     | Konkala, Yashwanth Kumar Reddy     | capgemini    | t
 377 | swapna.avula@capgemini.com                      | Swapna Avula                       | capgemini    | t
 382 | sriram-thiruvalangadu.kumaraswamy@capgemini.com | Kumaraswamy, Sriram Thiruvalangadu | capgemini    | t
 378 | shibananda.mishra@capgemini.com                 | Shibananda Mishra                  | capgemini    | t

## Related
- [[databases-moc]]
- [[create-new-instance]]
