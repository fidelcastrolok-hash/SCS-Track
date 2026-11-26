# Server Baseline -- fisher-Virtual-Machine

- Checkpoints: before-scs4.3 snapshot and server-baseline.txt on fisher-Virtual-Machine (172.18.162.111)
- Firewall (ufw): active; incoming deny, outgoing allow, routed deny; local-only 53, 631, 5432; 12 security updates waiting

| Rule | Why | Laptop |
| --- | --- | --- |
| ufw allow 22/tcp comment 'SSH remote administration - SCS4.3' | SSH remote administration session | port 22 sshd listening |
| ufw allow 80/tcp comment 'nGINX http web service - SCS4.3' | HTTP web service session | port 80 nginx listening |
| ufw allow 8069/tcp comment 'Odoo Web Service - SCS4.3' | Odoo web application session | port 8069 python3 listening |
| ufw allow 443/tcp comment 'HTTPS web service - SCS4.3' | HTTPS web service session | HTTPS rule in ufw |

| Part | Mine |
| --- | --- |
| Job line | 17 * * * * root /usr/local/sbin/scs-server-backup /srv/scs-backups |
