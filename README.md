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

When you start the role for the first time, then you do not yet know the token.
Therefore, containers with runner will be launched, but will not be registered.
You should find out your token in GitLab UI, set it to `gitlab_token` and run
the role again.

```yaml
gitlab_token: <your-token>
```

Ports for GitLab:

```yaml
gitlab_port_web: 80
gitlab_port_tls: 443
gitlab_port_ssh: 2222
```

Paths for GitLab:

```yaml
gitlab_volume_config: "/srv/gitlab/config"
gitlab_volume_logs: "/srv/gitlab/logs"
gitlab_volume_data: "/srv/gitlab/data"
```

Config path for runner containers:

```yaml
gitlab_runner_volume_config: "/srv/gitlab-runner/config"
```

Version of docker image with "Runner":

```yaml
gitlab_runner_image_version: "latest"
```

Number of containers with "Runner":

```yaml
gitlab_runner_count: 1
```

Dependencies
------------

Ansible roles:

* geerlingguy.pip
* geerlingguy.docker

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: gitlab
      gitlab_external_url: http://10.10.10.10
      gitlab_hostname: "gitlab.example.com"
      gitlab_token: UIoWFp0aNl_z9_iWhXab
      gitlab_runner_count: 3
```

License
-------

BSD

Author Information
------------------

Sedov Andrey [sedoy80@gmail.com]
