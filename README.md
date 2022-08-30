[![integration](https://github.com/usegalaxy-au/ansible-s3fs/actions/workflows/integration.yaml/badge.svg)](https://github.com/usegalaxy-au/ansible-s3fs/actions/workflows/integration.yaml)

galaxyproject.s3fs
==================

Ansible role for installing s3fs and mounting/managing s3 buckets.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

```
s3fs:
  access_key:
  secret_key:
  passwd_file: /etc/passwd-s3fs
  buckets:
    biorefdata:
      mountpoint: /cvmfs/data.galaxyproject.org
      prefix: /galaxy/v1/data.galaxyproject.org
      access_key:
      secret_key:
      options: "allow_other,use_cache=/tmp,max_stat_cache_size=100000,uid=33,gid=33,umask=002,url=https://s3.ap-southeast-2.amazonaws.com,endpoint=ap-southeast-2,public_bucket=1,enable_noobj_cache,no_check_certificate,kernel_cache,ensure_diskfree=10000"
```

Multiple buckets can be defined, with the bucket name being the dictionary key (In this example, biorefdata).

A prefix can be defined optionally.

The `access_key` and `secret_key` can be (optionally) defined per bucket. If not defined, the globally defined `access_key` and `secret_key` will be used.


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: galaxyproject.s3fs }

License
-------

MIT

Author Information
------------------

The Galaxy Project
