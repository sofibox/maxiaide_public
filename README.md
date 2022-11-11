MaxiAIDE is an AIDE wrapper tool to manage AIDE easily

See the original AIDE: https://github.com/aide/aide

To scan the system for file changes use the following:

`maxiaide scan -u -b` or `maxiaide scan -ub`

`-u, --update, --db-auto-update, --auto-update, --db-update: auto AIDE database for any changes`

`-b, --backup, --db-auto-backup, --auto-backup, --db-backup: auto backup old database with a timestamp for audit purpose`

To limit the scan to a specific path against the current database:

`maxiaide scan --limit /var/www/html/mywebapps.com `

To send an email report after the scan is completed:

`maxiaide scan --email`

where the email address needs to be defined correctly for the variable `ADMIN_EMAIL=user@tld.com` inside the script.
Email reports will only work when:

1) The scan result has at least one warning
2) The report email is correctly defined for the variable ADMIN_EMAIL=user@tld.com

You can add custom rules in `conf/custom_rules` by opening with an editor you like or by using the following command:

`maxiaide editrule`

This will open a nano editor for you to insert a new rule. When you quit the editor, it will prompt you to validate the new 
rule if the custom rule file has changed. To manually update the new rule, run `maxiaide updaterule`

When you run `maxiaide update-rule` it will update the new rules into `/etc/aide/aide.conf.d/*`

To overwrite aide scan catchall rule from list of rules at `/etc/aide/aide.conf.d/*`, add the following line into `conf/custom_rules` on top:

`/ MaxiRule`

where `/` is the root path to scan (as a catchall rule)
and `MaxiRule` is an example of a rule variable that must be defined in `conf/custom_aide.conf`

eg: in `conf/custom_aide.conf`, `MaxiRule` is defined as:

`MaxiRule = sha512+ftype`

You can add more custom rules definition in `conf/custom_aide.conf` like you normally do in `aide.conf`

Look at `conf/custom_rules.sample` for sample rule.

See `maxiaide --help` for more actions and options.