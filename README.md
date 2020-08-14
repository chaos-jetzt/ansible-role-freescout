Role Name
=========

Install and configure [freescout-helpdesk](https://github.com/freescout-helpdesk/freescout) (to an extent) on your host(s).

Requirements
------------

PHP is required for the installation, you could use geerlingguy's role for example: https://github.com/geerlingguy/ansible-role-php.

While not technically required for the installation, to run Freescout you will also need to have a webserver such as nginx installed. geerlingguy also created a role here (https://github.com/geerlingguy/ansible-role-nginx) for nginx. An example nginx config for freescout can be found here: https://github.com/freescout-helpdesk/freescout/wiki/Installation-Guide#61-nginx

Role Variables
--------------

TODO

<!-- A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well. -->

Dependencies
------------

<!-- A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles. -->

Example Playbook
----------------

```yml
---
- hosts: all
	roles:
		- chaos-jetzt.freescout
	vars:
		freescout_basedir: /var/www/freescout
		freescout_source: git
		freescout_config:
			- name: db_connection
				value: mysql
			- name: db_host
				value: localhost
			- name: db_port
				value: 3306
			- name: db_database
				value: freescout
			- name: db_username
				value: root
			- name: db_password
				value: root
			- name: app_url
				value: "http://localhost:8080"
		freescout_admin_user:
			firstName: Chaos
			lastNaMe: Jetzt
			email: info@example.org
			password: secret
```

# License

BSD 3 Clause

# Author Information

Initially written by [e1mo](https://github.com/e1mo) for the [chaos.jetzt](https://chaos.jetzt) project. The git-repo lives at [https://github.com/chaos-jetzt/ansible-role-freescout](https://github.com/chaos-jetzt/ansible-role-freescout)
