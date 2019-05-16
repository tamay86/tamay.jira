Ansible Role: tamay.jira
=========

This role installs only [jira](https://www.atlassian.com/software/jira). It does not install and configure a remote database or a reverse proxy. 

Requirements
------------

None.

Role Variables
--------------

List of all variables, including default values.
    
    jira_version: 8.1.0
    
Version of jira that should be installed.
    
    jira_base_dir: /opt/atlassian/jira

Path where jira will be installed.

    jira_data_dir: /var/atlassian/application-data/jira

Path where jira will keep it's application data.

    jira_server_connector:
      name: default
      proxyName: "{{ ansible_fqdn }}"

Configures the connector in ```server.xml```. Possible values are ```default```, ```http-proxy``` and ```https-proxy```. For explanation see contents of ```server.xml```.
Most commonly used is **https-proxy** for usage with a reverse proxy, that terminates SSL, such as *httpd*, *nginx*, or *haproxy*.

**proxyName** is only used with ```http-proxy``` and ```https-proxy```.

Dependencies
------------

None.

Example Playbook
----------------

    ---
    
    - hosts: all
    
      vars:
        jira_version: 8.1.0
    
      roles:
      - tamay.jira

License
-------

MIT

Author Information
------------------

tamay.mueller@gmail.com