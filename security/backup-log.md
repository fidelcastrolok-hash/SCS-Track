# Backup and Restore Log -- fisher-Virtual-Machine

- Schedule & job: 17 * * * * root /usr/local/sbin/scs-server-backup /srv/scs-backups (mode 700, root-owned)
- Latest archive: scs-backup-fisher-Virtual-Machine-20261126-141701.tar.gz (6,373,068 bytes / 6.1 MB, fingerprint good, pg:1, mariadb:0)
- Restore test: 2026-11-26 14:42:42 -> kijiji-fisher-restored-2026-11-26 (files in /var/tmp/scs-restore-20261126-143923), took 200s
- Findings: 20 customer invoices matched live kijiji-fisher (Upendo Primary School invoice checked); filestore reported 7 of 604 stored files found in restored copy; /etc/cron.d/scs-backup and /etc/ufw/user.rules matched live files; cleaned with sudo scs-server-backup --clean-restores
