supervisord
======

This role installs supervisord, a simple process manager.

Documentation: http://supervisord.org/

Role Variables
--------------

* **supervisord_programs:** A list of programs to monitor. Check example for more details about the available parameters per entry.
* **supervisord_log_path:** Path to store output from programs (default: "/var/log").

Example Playbook
----------------

    - hosts: servers
      roles:
        - { 
          role: supervisord
          supervisord_log_path: '/var/log/supervisord'
          supervisord_programs:
            - name: 'consumer01'
              command: 'app/console rabbitmq consumer'
              directory: '/var/www/symfony-app'
              numprocs: 1
              autostart: true
              autorestart: true
              user: 'www-data'
              stderr_logfile: 'supervisord-consumer01.err.log'
              stdout_logfile: 'supervisord-consumer01.out.log'
            - name: 'app'
              process_name: 'app.py'
              ...
        }

License
-------

BSD
