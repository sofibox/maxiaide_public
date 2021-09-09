MaxiAIDE is an AIDE wrapper tool to manage AIDE easily

See the original AIDE: https://github.com/aide/aide

To scan system use the following:

`maxiaide scan -u -b`

`-u: auto update database`

`-b: auto backup old database with timestamp`

You can add custom rules in `/conf/custom_rules`:

`maxiaide edit-rule`

To overwrite aide scan catchall rule from `/etc/aide/aide.conf.d/*`, add the following line into custom rule on top:

`/ MaxiRule`

where `/` is the root path to scan
and `MaxiRule` is an example of rule that must be defined in conf/custom_aide.conf`

you can add more rules in conf/custom_aide.conf like you normally do in `aide.conf`

then run `maxiaide update-rule` to update the new rules into `/etc/aide/aide.conf.d/*`

See `maxiaide --help` for more actions and options.