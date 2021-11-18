# Ansible Roles

## Testing

```bash
vagrant up --provision
```

## Linting

Install with `apt install ansible-lint`.

```bash
ansible-lint main.yml
```

## Connecting to Vagrant Box

```bash
ssh vagrant@192.168.60.51 -p 2891 -i ~/.vagrant.d/insecure_private_key
```

[Vagrant Ansible Intro](https://www.vagrantup.com/docs/provisioning/ansible_intro)

# Caching Apt

Use `~/.cache` or `$XDG_CACHE_HOME` from [basedir spec](http://standards.freedesktop.org/basedir-spec/basedir-spec-latest.html) as a shared folder for `/var/cache/apt` on the guest VM's.

# Install Locations

- Command Line tools e.g. `julia`, `texlive`, that nevertheless have their own folder structure, go into `/usr/local` e.g. `/usr/local/texlive`
- GUI programs that have their own folder structure go in `/opt` e.g. `/opt/Postman`