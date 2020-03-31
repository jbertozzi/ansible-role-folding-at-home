# folding-at-home

Configure Folding@Home on a Linux machine.

The role only configure the client.

## Role Variables

* `folding_at_home_install_fahclient`: Install and configure fahclient (default: `true`)
* `folding_at_home_install_fahcontrol`: Install and configure fahcontrol (default: `false`, not implemented)
* `folding_at_home_install_fahviewer`: Install and configure fahviewer (default: `false`, not implemented)
* `folding_at_home_fah{client,control,viewer}_url`: URLs of fahclient package per supported OS ([default variable](defaults/main.yml))
* `folding_at_home_proxy`: use a proxy to connect remote servers (default: None) 
* `folding_at_home_user`:  User to run software (default: `nobody`, seems to be ignored anyway since it is hardcoded in init script)
* `folding_at_home_team`: team number (default: `0`)
* `folding_at_home_passkey`: passekey (default: `""`)
* `folding_at_home_power`: power (`light`|`medium`|`full`, default: `medium`)
* `folding_at_home_use_gpu`: use GPU (defaul: `false`)
* `folding_at_home_tmp_dir`: Download directory (default: `/var/tmp`)

## Example Playbook

```
---
- hosts: servers
  roles:
     - role: folding-at-home
      vars:
        folding_at_home_team: 8767858458
        folding_at_home_passkey: secret
```

## License

BSD

## Author Information

Jérémy Bertozzi <jeremy.bertozzi@gmail.com>
