# Ansible role: CRON

Install and deploy cron jobs and cron vars.

A copy of [robertdebock/ansible-role-cron](https://github.com/robertdebock/ansible-role-cron).

Only tested on Archlinux.

## Usage
Override [defaults](https://github.com/lunics/ansible_role_cron/blob/main/defaults/main.yml)
```yaml
cron_jobs: []
  - name:       description of the task
    day:        1-15          # for the first part of the month
    hour:       23            # in the 23rd hour
    job:        ls -l         # run this command
    minute:     "*/10"        # every 10 minutes
    user:       root          # for a specific user
    cron_file:
    month:
    weekday:
    special_time:
    state:
```
```yaml
cron_vars: []
  - name:   PATH
    value:  /usr/bin:/bin:/usr/local/bin
    user:   root
```
TODO
- replace tasks/config.yml lineinfile by templates
- replace cron.packages by cron_packages
