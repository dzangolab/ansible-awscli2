ansible-awscli
=========

This role setups AWS CLI version 2.


Role Variables
--------------

Variables to deploy role are listed below.

- AWS CLI profiles with credentials

AWS CLI profiles can be given as follows:

```yml
awscli_users:
  # Add the user 'johnd'
  - user: johnd
    state: present
    profiles:
      - name: default
        aws_access_key_id: XXXXXXXXXXXXXXXXXXXX
        aws_secret_access_key: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
        output: json
        region: ap-northeast-1
  # Remove the user 'johnd'
  - user: johnd
    state: absent
```

Example Playbook
----------------

```yml
- name: Install aws-cli
  hosts: all
  roles:
    - name: Install aws-cli
      role: dzangolab.awscli2
  tags:
    - awscli
  vars:
    awscli_users:
      # Add the user 'johnd'
      - user: johnd
        state: present
        profiles:
          - name: default
            aws_access_key_id: XXXXXXXXXXXXXXXXXXXX
            aws_secret_access_key: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
            output: json
            region: ap-northeast-1
      # Remove the user 'johnd'
      - user: johnd
        state: absent
```

License
-------

MIT
