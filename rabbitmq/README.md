rabbitmq
========

This role installs and configures [RabbitMQ](https://www.rabbitmq.com/).

Role Variables
--------------

* **rabbitmq_plugins**: A comma-separated list of plugins to install

Example Playbook
----------------

    - hosts: servers
      roles:
        - { 
          role: rabbitmq
        }

License
-------

BSD
