Role Name
=========

Install and configure apache.

Role Variables
--------------

    # Packages for apache
    lwiesel_apache_packages:
      - apache2-doc
      - apache2-utils
      - apache2-mpm-itk
      - libapache2-mod-php5
    
    # Modules for apache
    lwiesel_apache_module_enable:
      - alias
      - rewrite
      - php5
    lwiesel_apache_module_disable: []
    
    # php configuration
    lwiesel_php_conf_template: php.ini.j2
    
    # Apache vhosts configuration
    lwiesel_apache_vhost_conf_template: vhost.conf.j2
    lwiesel_apache_vhosts:
      - servername: test.dev
        index: index.php
        documentroot: /var/www/test
        directory_extra:
          - RewriteEngine On
    
    lwiesel_apache_site_disable:
      - 000-default
      - default-ssl
    lwiesel_apache_site_enable:
      - test.dev

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    roles:
        - { role: lwiesel.apache, tags: apache }

License
-------

Licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
