# ansible-nginx

*Installs and globally configures nginx.*

See [default variables](defaults/main.yml) for details.

## Requirements

* Ansible 2.0+
* One of these target systems:
    * Debian jessie
    * Ubuntu 16.04

## Example

```
- role: nginx
  nginx_delete_default_site: yes
  nginx_override_conf: |
    server_names_hash_bucket_size 128;
```
