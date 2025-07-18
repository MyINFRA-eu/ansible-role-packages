# MyINFRA.eu Ansible Role: packages

[![MyINFRA.eu logo](https://raw.githubusercontent.com/MyINFRA-eu/.github/main/logo/myinfra-logo-grey.svg)](https://myinfra.eu)


## About

Install debian based packages on the system.


## Support us

We invest a lot of resources and time into creating these ansible roles. You can supports us by [sponsoring this project](https://github.com/MyINFRA-eu#sponsorship).

We highly appreciate you mentioning us or our projects on you website, social media, ...


## Statistics

**Releases**

![GitHub Release](https://img.shields.io/github/v/release/MyINFRA-eu/ansible-role-packages?style=flat)
![GitHub Release Date](https://img.shields.io/github/release-date/MyINFRA-eu/ansible-role-packages?style=flat)
![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/MyINFRA-eu/ansible-role-packages/total?style=flat)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/MyINFRA-eu/ansible-role-packages/latest/total?style=flat)

**Commits/Activity**

![GitHub branch status](https://img.shields.io/github/checks-status/MyINFRA-eu/ansible-role-packages/main?style=flat)
![GitHub last commit](https://img.shields.io/github/last-commit/MyINFRA-eu/ansible-role-packages?style=for-the-badge?style=flat)
![GitHub commit activity](https://img.shields.io/github/commit-activity/w/MyINFRA-eu/ansible-role-packages?style=flat)
![GitHub commits since latest release](https://img.shields.io/github/commits-since/MyINFRA-eu/ansible-role-packages/latest?style=flat)
![GitHub contributors](https://img.shields.io/github/contributors/MyINFRA-eu/ansible-role-packages?style=for-the-badge?style=flat)

**Repository**

![GitHub repo file or directory count](https://img.shields.io/github/directory-file-count/MyINFRA-eu/ansible-role-packages?style=flat)
![GitHub repo size](https://img.shields.io/github/repo-size/MyINFRA-eu/ansible-role-packages?style=flat)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/MyINFRA-eu/aansible-role-packages?style=flat)
![GitHub language count](https://img.shields.io/github/languages/count/MyINFRA-eu/ansible-role-packages?style=flat)
![GitHub top language](https://img.shields.io/github/languages/top/MyINFRA-eu/ansible-role-packages?style=flat)

**Ansible Galaxy**

![Ansible Collection Version](https://img.shields.io/ansible/collection/v/myinfra_eu/packages?style=flat)
![Ansible Collection Downloads](https://img.shields.io/ansible/collection/d/myinfra_eu/packages?style=flat)
![Ansible Role](https://img.shields.io/ansible/role/d/myinfra_eu/packages?style=flat)

**Owner**

![GitHub Sponsors](https://img.shields.io/github/sponsors/Dennis-de-Houx?style=for-the-badge)
![GitHub followers](https://img.shields.io/github/followers/Dennis-de-Houx?style=for-the-badge)
![GitHub User's stars](https://img.shields.io/github/stars/Dennis-de-Houx?style=for-the-badge)

**Organisation**

![GitHub Org's stars](https://img.shields.io/github/stars/MyINFRA-eu?style=for-the-badge)


## Requirements

None.


## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

### autoclean

Auto cleanup repositories of old package information.

> value needs to be a boolean (true|false)

**example:**
```yml
packages:
  autoclean: false
```

### autoremove

Auto remove unused packages from the system.

> value needs to be a boolean (true|false)

**example:**
```yml
packages:
  autoremove: false
```

### recommends

Install recommended packages.

> value needs to be a boolean (true|false)

**example:**
```yml
packages:
  recommends: false
```

### upgrade

Upgrade system to newer version.

Values:
- no = leave the system alone
- dist = perform a dist-upgrade
- full = perform a full-upgrade
- yes or safe = perform a safe-upgrade

**example:**
```yml
packages:
  upgrade: "no"
```

### state

The state of the installed packages.

Values:
- present = make sure the package is installed
- latest = make sure the package has the latest version and is updated

**example:**
```yml
packages:
  state: "present"
```

### Cache settings

Set if cache is being used and for how long the cache is valid.

#### update

Update cache before installing new packages.

> value needs to be a boolean (true|false).

#### time

> value needs to be a integer, for example "3600" means 3600 seconds or 1 hour.

**example:**
```yml
packages:
  cache:
    update: true
    time: 3600
```

### install

List of packages to install that need to be installed on the system.

> Value needs to be a array list.

**example:**
```yml
packages:
  install:
    - "sshd"
    - "curl"
    - "htop"
```

### remove

List of packages to be removed from the system.

> Value needs to be a array list.

**example:**
```yml
packages:
  install:
    - "laptop-detect"
```

### services

Check if services are enabled/disable and running/stopped

#### enabled

Make sure the services is enabled or disabled on startup

> value needs to be a boolean (true|false).

### state

Make sure the service is running or stopped or ...

Values:
- reloaded
- restarted
- started
- stopped

**example:**
```yml
packages:
  services:
    sshd:
      enabled: true
      state: "started"
```

### Full example

**example:**
```yml
packages:
  autoclean: false
  autoremove: false
  recommends: false
  upgrade: "no"
  state: "present"
  cache:
    update: true
    time: 3600
  install:
    - "sshd"
    - "htop"
    - "curl"
  remove:
    - "laptop-detect"
  services:
    sshd:
      enabled: true
      state: "started"
```

## Dependencies

None.


## Example Playbook

```
- hosts: all
  vars_files:
    - vars/main.yml
  roles:
    - { role: myinfra_eu.packages }
```


## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.


## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.


## Security Vulnerabilities

Please review [our security policy](https://github.com/MyINFRA-eu/ansible-role-packages/security/policy) on how to report security vulnerabilities.


## Credits

- [Dennis de houx](https://github.com/Dennis-de-Houx)
- [All Contributors](https://github.com/MyINFRA-eu/ansible-role-packages/contributors)


## Copyright

- (c) 2025 MyINFRA.eu ~ [https://myinfra.eu](https://myinfra.eu)
- (c) 2025 All In One ~ [https://all-in-one.be](https://all-in-one.be)
- (c) 2025 Dennis de houx ~ [https://dehoux.be](https://dehoux.be)


## Inspiration

During development some roles in Ansible Galaxy/Github also inspired me,
thanks to the following developers for the inspiration:

- [geerlingguy](https://github.com/geerlingguy/)


## License

The Attribution-NonCommercial-NoDerivatives 4.0 International License. Please see [License File](LICENSE.md) for more information.
