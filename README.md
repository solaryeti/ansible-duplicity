# Ansible - Duplicity
## Description

Ansible role for making remote, incremental, encrypted backups with [duplicity](http://duplicity.nongnu.org/).

This role has been developed specifically for backing up servers over ftp in Hetzner's datacenter. Although all settings are configurable, the assumption is that a backup will be made to a remote ftp server.


## Variables

```yaml
---
# FTP settings
backup_host: username.your-backup.de
backup_user: username
backup_user_pass: password

# Backup settings
backup_dirs:
  - /foo
  - /bar
backup_time: daily # corresponding to cron.daily, cron.hourly, or cron.weekly, cron.monthly
time_period_incremental_backups: 1W
time_period_keep_backups: 2M

# Email address for error reports
backup_email: user@example.com

# Passphrase for gpg key
encrypt_passphrase: supersecretpassphrase

# The gpg key name to use for encryption
encrypt_key: user@example.com

# The local path to the gpg key to be copied to the server
gpg_pub_key: /path/to/gpg-key
```

For full details see `defaults/main.yml`.

## Contributors

Feel free to contribute by sending pull requests.

## License

This role is licensed under a BSD-style license. See LICENCE for details.
