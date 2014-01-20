ansible-logstash-play
=====================

Ansible Playbook to Deploy a Vanilla Logstash Install

## What this role does

This role simply installs Java and the Logstash JAR file as well as the daemonize package used
with the provided init script. Povides a completely blank logstash.conf. I use the daemonize package
to help simplify the init script as it tends to be easier for people to reason through that aren't as
experienced with the Fedora / RHEL based init system.


## What this role does not do

It does not configure logstash. There are many complex and different ways to configure it, so I leave
that up to the experties of the end user to adjust the config the way they see fit. Does not set logstash
to start at boot.

## Default Vars

    #File defaults/main.yml
    ---
    ansible_logstash_jar: logstash-1.3.3-flatjar.jar
    ansible_logstash_config_file: /opt/logstash/conf/logstash.conf
    ansible_logstash_log_file: /opt/logstash/logs/logstash.log

These vars should be pretty self explanatory.

ansible_logstash_jar is the version of logstash to pull pull down

ansible_logstash_config_file is the default configuration file directory and file name

ansible_logstash_log_file is the default logfile location and name

All three of these are used in the init script template that is provided.

## Working Distros

This has been tested and working with Fedora 18,19, and 20

### Feedback and constructive critisim is much appreciated.
