# Ansible role: CRON

Install and deploy cron jobs and cron vars.

A copy of [robertdebock/ansible-role-cron](https://github.com/robertdebock/ansible-role-cron).

Only tested on Archlinux.

## Usage
Override [defaults](https://github.com/lunics/ansible_role_cron/blob/main/defaults/main.yml)
```yaml
cron_jobs: []
  - name:   job title     # required, description of the job
    job:    ls -l         # required, command ran
    day:    1-15          # for the first part of the month
    hour:   23            # in the 23rd hour
    minute: "*/10"        # every 10 minutes
    user:   root          # optional, default = root; job for a specific user
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
- implement task/cron_jobs.yml:templatecron_files
