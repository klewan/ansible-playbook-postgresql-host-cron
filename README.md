Ansible Playbook: postgresql-host-cron
======================================

Configure PostgreSQL database server cron

Supported OS:
-------------
* RedHat
* CentOS
* OracleLinux

Requirements
------------

This playbook requires `postgresql-host-cron` and `postgresql-nsr-backup` roles.

`$ ansible-galaxy install -r roles/requirements.yml`

Examples
--------

    $ ansible-playbook playbook.yml --list-tasks
    $ ansible-playbook playbook.yml --list-tags

Complete PostgreSQL database server cron configuration

    $ ansible-playbook playbook.yml

Copy cron scripts only, but DO NOT change anything in cron

    $ ansible-playbook playbook.yml --extra-vars='{"postgresql_host_cron_copy_scripts": true, "postgresql_host_cron_manage_cron_jobs": false}'

Setup cron jobs

    $ ansible-playbook playbook.yml --tags=postgresql_host_cron_setup --extra-vars='{"postgresql_host_cron_copy_scripts": true, "postgresql_host_cron_manage_cron_jobs": true}'

Disable (comment out) all cron jobs managed by Ansible

    $ ansible-playbook playbook.yml --extra-vars='{"postgresql_host_cron_copy_scripts": false, "postgresql_host_cron_disable_jobs": true}'

Enable all cron jobs managed by Ansible

    $ ansible-playbook playbook.yml --extra-vars='{"postgresql_host_cron_copy_scripts": false, "postgresql_host_cron_disable_jobs": false}'

	
License
-------

GPLv3 - GNU General Public License v3.0

Author Information
------------------

This playbook was created in 2018 by [Krzysztof Lewandowski](mailto:Krzysztof.Lewandowski@fastmail.fm).


