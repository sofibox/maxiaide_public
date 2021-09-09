# maxiaide_public

MaxiAIDE is an AIDE wrapper tool to manage AIDE easily

See the original AIDE: https://github.com/aide/aide

To scan system use the following:

`maxiaide scan -u -b`

`-u: auto update database`

`-b: auto backup old database with timestamp`

You can add custom rules in `/conf/custom_rules`:

`maxiaide edit-rule`

then run maxiaide `update-rule` to update the new rule into `/etc/aide/aide.conf.d/*`

See maxiaide --help for more options.