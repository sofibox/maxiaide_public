Maxi AIDE Documentation

MaxiAIDE is an AIDE wrapper tool to manage AIDE easily

See the original AIDE: https://github.com/aide/aide

Author: Arafat Ali | Email: arafat@sofibox.com | (C) 2019-2022

Usage:

maxiaide <-SHORT_OPTIONS/--LONG_OPTIONS>
maxiaide <ACTIONS> <-SHORT_OPTIONS/--LONG_OPTIONS>

example:

maxiaide scan --verbose --update --email --backup or maxiaide scan -vueb
maxiaide scan --limit /var/www/html/mywebapps.com --email or maxiaide scan -el /var/www/html/mywebapps.com

OPTIONS:

  -h, --help, /?, ?
        This is a help text.

  -v, -V, --version, version, ver
        Show version information

  -t, --test
        Provide a unit test

ACTIONS:

  scan, check, compare

      Run system scan for any file or folder changes based on rule from aide.conf.
      In order to update AIDE database automatically after scanning, use the following options:
      -a, --auto-update

      OPTIONAL PARAMETER(S):

          -j, --cron, --cronjob
          Run the scan in cronjob mode

          -v, --verbose
          Run the scan in verbose mode

          -d, --debug
          Run the scan in debug mode

          --log-level <LOG_LEVEL>
          Run the scan as in <LOG_LEVEL> mode, where LOG_LEVEL can be one of the following levels:
          error, warning, notice, info, rule, config, debug, trace
          Note that when this option is present, it will ignore both -v and -d options

          -a, -u, --update, --db-auto-update, --auto-update, --db-update
          Auto update AIDE database after scanning

          -b, --backup, --db-auto-backup, --auto-backup, --db-backup
          Automatically archive or backup existing AIDE database with timestamp after scanning

          -f, -p, -l, -r, --file, --path, --limit, --regex <PATH or REGEX>
          Compare or limit specific file, path or use regex comparison against current database

          -e, --email
          Enable email report. Even if this option is present, it will not send email if there is no warning appear
          from the scan. Please make sure that the email report format is valid or the script will prompt to correct it


  init

      Initialize config file and database. This will also back up existing AIDE config file
      Note that this action will remove the latest AIDE database and restore the following files into original state:
      1) The AIDE custom rules at conf/custom_rules
      2) The AIDE custom config at conf/custom_aide.conf

  update-rule, updaterule

      Update the temporary custom rule template from conf/custom_rules into AIDE default rule path specified in
      AIDE_DEFAULT_RULES_PATH
      Note that this action will automatically check the modified config or rules

  clearlog, removelog, cleanlog

       Clean old logs except the latest log

  latestlog, lastlog, lastreport

       Read the latest generated report

  edit-rule, edit-rules, editrule

      Edit the existing rule file via an editor. When the editor is quit, it will prompt to check the new rules.

  edit-conf, edit-config
      Edit AIDE custom config file from conf/custom_aide.conf