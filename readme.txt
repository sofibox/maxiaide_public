Maxi AIDE Documentation

MaxiAIDE is an AIDE wrapper tool to manage AIDE easily

See the original AIDE: https://github.com/aide/aide

Author: Arafat Ali | Email: arafat@sofibox.com | (C) 2019-2021

Usage:

maxiaide <-SHORT_OPTIONS/--LONG_OPTIONS>
maxiaide <ACTIONS> <-SHORT_OPTIONS/--LONG_OPTIONS>

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

          -a, -u, --update, --db-auto-update, --auto-update, --db-update
          Auto update AIDE database after scanning

          -b, --backup, --db-auto-backup, --auto-backup, --db-backup
          Automatically archive or backup existing AIDE database with timestamp after scanning

           -c, -f, -p, -l, --compare, --file, --path, --limit <PATH>
           Compare specific file or path against current database

           -e, --email
           Enable email report. Even if this option is enabled, it will only send email if there is one or more
           warning appear from the scan. Please make sure that the email report format is valid or the script will prompt
           to correct it

  init

      Initialize config file and database. This will also backup existing AIDE config file
      Note that this action will automatically run another action called update-rule


  update-rule, updaterule

      Update custom rule from /conf/custom_rules.

  clearlog, removelog, cleanlog

       Clean old logs except the latest log

  latestlog, lastlog, lastreport

       Read the latest generated report

  edit-rule, edit-rules, editrule

      Automatically open custom rule file and edit them via editor