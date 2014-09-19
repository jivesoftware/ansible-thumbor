Ansible Thumbor
=========

`thumbor` is an [ansible](http://www.ansible.com) role which:

* installs nginx
* installs thumbor
* configures thumbor
* starts both as services

Installation
------------

Using `ansible-galaxy`:

```
$ ansible-galaxy install savagegus.thumbor
```

Using `git`:

```
$ git clone https://github.com/jivesoftware/ansible-thumbor.git
```

Role Variables
--------------

```
thumbor_aws_access_key: ''
thumbor_aws_secret_key: ''
thumbor_aws_loader_bucket: ''
thumbor_aws_version: a0c4bcc02601af317072adab32ce0be14d0cd492
thumbor_server_name: localhost
thumbor_user: thumbor
thumbor_group: thumbor
thumbor_home: /home/thumbor
thumbor_config_file: /etc/thumbor.conf
thumbor_key_file: /etc/thumbor.key
thumbor_log_file: /var/log/thumbor
thumbor_working_directory: /var/lib/thumbor
thumbor_default: /etc/default/thumbor
thumbor_server_name: localhost
thumbor_bind_address: 127.0.0.1
thumbor_loader: thumbor_aws.loaders.s3_loader
```

Dependencies
------------

franklinkim.nginx

Example Playbook
----------------

```
- hosts: all
  roles:
    - ansible-thumbor
  vars:
    nginx_remove_default: yes
    nginx_worker_processes: 1
    nginx_worker_connections: 1024
    thumbor_aws_access_key: XXX
    thumbor_aws_secret_key: XXX
    thumbor_aws_loader_bucket: XXX
```

Testing
_______

```
$ git clone https://github.com/jivesoftware/ansible-thumbor.git
$ cd ansible-thumbor
$ vagrant up
```

Contributing
____________

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

License
_______

Copyright (c) Jive Software under the Apache license.
