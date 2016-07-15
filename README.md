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

## Useful snippets

Unless you set `nginx_generate_snippets` to `no`, a collection of useful snippets will be placed in
`/etc/nginx/snippets`. You can then include them in your configuration.

* `disallow_robots.conf`: Defines a `/robots.txt` location that disallows all robots.

## Catchall

If `nginx_catchall_enable` is set, a site acting as a fallback for all hostnames will be enabled.
This catchall config has multiple purposes, like answering [ACME][acme] challenges or redirecting
to HTTPS.

[acme]: https://github.com/hsoft/ansible-acme-nginx
