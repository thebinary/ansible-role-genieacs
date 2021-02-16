thebinary.genieacs
==================

Ansible role to install and manage [GenieACS](https://genieacs.com/). 
Supports:
- Install Type: source build (github repo)
- OS: ubuntu

Role Variables
--------------

__VARS__

| Variable         | Definition                                                | Default                              |
|------------------|-----------------------------------------------------------|--------------------------------------|
| user             | system user for genieacs                                  | genieacs                             |
| group            | system group for genieacs                                 | genieacs                             |
| repo_url         | github repo url to install genieacs from                  | https://github.com/genieacs/genieacs |
| repo_version     | github branch/tag to build and install                    | v1.2.3                               |
| genieacs_env     | Override/Additional environment vars for genieacs service | {}                                   |
| install_dir      | GenieACS dir to store env and ext scripts                 | /opt/genieacs                        |
| log_dir          | GenieACS log dir                                          | /var/log/genieacs                    |
| source_bin_dir   | path to create genieacs binaries links                    | /usr/local/bin                       |

__DEFAULTS__

| Variable              | Definition                                        | Defaults                                |
|-----------------------|---------------------------------------------------|-----------------------------------------|
| node_repo_version     | 12.x                                              | NodeJS version to install for genieacs  |
| npm_path              |                                                   | /usr/bin/npm                            |
| rebuild               | force rebuilding and reinstall of genieacs source | false                                   |
| defaults_genieacs_env | defaults/required env vars for genieacs service   | _dict of env vars_                      |
| ext_dir               | path for genieacs ext scripts                     | {{ install_dir/ext }}                   |
| source_dir            | path to clone genieacs repo into                  | /usr/local/src/genieacs                 |
| dist_install_dir      | path to install source build of genieacs          | /usr/local/share/genieacs               |


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
  - hosts: genie
    roles:
      - role: thebinary.genieacs
        repo_version: xmpp
        genieacs_env:
          GENIEACS_XMPP_JID: genie@example.org
          GENIEACS_XMPP_PASSWORD: xmpppassword
```

License
-------

MIT

Author Information
------------------

[TheBinary](https://github.com/thebinary)
