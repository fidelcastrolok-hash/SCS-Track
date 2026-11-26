# Server Baseline -- fisher-Virtual-Machine

- Host: fisher-Virtual-Machine (172.18.162.111), operator: fisher
- Firewall (ufw): active; default incoming deny, outgoing allow, routed deny
- Allowed ports: 22/tcp (SSH), 80/tcp (nginx HTTP), 8069/tcp (Odoo web), 443/tcp (HTTPS)
- Local-only listeners: 53 (systemd-resolve), 631 (cupsd), 5432 (postgres)
- Startup & updates: 118 enabled units; unattended-upgrades on; 12 security updates waiting when baseline-look ran (fisher/admin applies pending updates during maintenance windows)
