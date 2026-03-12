---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/snippets
---

# Default.conf nginx   vmpamkeydev01

server {
    server_name localhost;
    listen 80;
#    listen \[::\]:80;

    location /docs {
        allow 127.0.0.1;
        allow ::1;
        deny all;

        alias /srv/docs;
        index index.html;
    }

    location /nginx_status {
        stub_status on;
        access_log off;
        allow 127.0.0.1;
        allow ::1;
        deny all;
    }
}

## Related
- [[devops-moc]]
- [[useful-commands]]
- [[direct-connect]]
- [[aws-command-line]]
