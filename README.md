# Ansible Role: Munin-Contrib [![Build Status](https://travis-ci.org/deveth0/ansible-munin-contrib.svg?branch=master)](https://travis-ci.org/deveth0/ansible-munin-contrib)

Checks out the [munin-contrib](https://github.com/munin-monitoring/contrib) Repository and links the configured plugins to /etc/munin/plugins

## Installation

You can either use ansible-galaxy to install this role:

    ansible-galaxy install deveth0.munin-contrib

Or checkout this git-repository to your roles directory:

    git clone https://github.com/deveth0/ansible-munin-contrib.git deveth0.munin-contrib

## Role Variables

Available variables are listed below:

    path: The path (basepath /plugins/) to the plugin in contrib-repository

    target:  The target name for the plugin
    
e.g. if you want to link [/plugins/apache/apache_watch_](https://github.com/munin-monitoring/contrib/blob/master/plugins/apache/apache_watch_) to /etc/munin/plugins/apache_watch_foo:

    - { path: 'apache/apache_watch_', target: 'apache_watch_foo' }

    

## Dependencies

No dependencies required

## Example Playbook


- name: Install munin-contrib plugins
  hosts: all

  roles:
    - role: deveth0.munin-contrib
      contrib_plugins:
        - { path: 'mail/dovecot', target: 'dovecot' }
        - { path: 'mail/postfix_filtered', target: 'postfix_filtered' }
        - { path: 'mail/mail_connections', target: 'mail_connections' }
        - { path: 'mail/postfix_mail_stats', target: 'postfix_mail_stats'}
        - { path: 'mail/postfix_mailstats', target: 'postfix_mailstats'}
        - { path: 'mail/dovecot', target: 'dovecot'}
       



## License

Apache License 2.0

## Author Information

This Role was created by [Alex Muthmann](http://dev-eth0.de).
