Role gitlab
===========

Run GitLab.

Requirements
------------

None

Role Variables
--------------

Required:

```yaml
gitlab_external_url: http://<your-host>"
gitlab_hostname: "gitlab.<your-company>.com"
```

Optional:

```yaml
gitlab_port_web: 80
gitlab_port_tls: 443
gitlab_port_ssh: 2222

gitlab_volume_config: "/srv/gitlab/config"
gitlab_volume_logs: "/srv/gitlab/logs"
gitlab_volume_data: "/srv/gitlab/data"
```

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: gitlab
      gitlab_external_url: http://10.10.10.10
      gitlab_hostname: "gitlab.example.com"
```

License
-------

BSD

Author Information
------------------

Sedov Andrey [sedoy80@gmail.com]
