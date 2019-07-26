# nginx-conf

[![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)][license]
![Posix compatible](https://img.shields.io/badge/POSIX-compatible-brightgreen)

Easy to use *nginx* configuration manager. It can:
* Create new virtual hosts configuration
* Use various pre-defined virtual hosts templates
* Initialize new virtual hosts from git repositories

## Requirements
* [nginx]

### Optional
* git - For cloning git repositories for virtual hosts
* composer - For creating bootstraps of various composer projects

## Installation
* Clone this repository
``
git clone https://github.com/KubqoA/nginx-conf.git
``
* Modify the predefined constants in the `nginx-conf` script
* Modify any configuration such as the PHP FPM socket in `conf.d` directory
* Copy `conf.d` directory into your nginx path (e.g. /etc/nginx)

# Usage

This script must be run as root.

Usage:
``
./nginx-conf [OPTIONS] <domain>
``

Available options:
* -h,--help                     Print this help information
* -V,--version                  Print version info and exit
* -v,--verbose                  Use verbose output
* -c,--certdomain <certdomain>  SSL certificate domain to be used (defaults to <domain>)
* -d,--directory <directory>    Directory for the virtual host (defaults to /srv/www/<domain>
* --skip-directory-creation     Skip directory creation
* -g,--git <repository>         Git repository to clone to the virtual host directory, ignored when -s is used
* -o,--owner <owner>            User and group owner of the virtual host directory (defaults to www-data:www-data)
* -t,--type <type>              Type of the virtual host configuration to be used
* -s,--create-sftp-user         Create a new user for SFTP access for the virtual host

## License

`nginx-conf` is released under [GNU General Public License v2][license]

Copyright (C) 1989, 1991 Free Software Foundation, Inc.

[license]: https://www.gnu.org/licenses/gpl-2.0.en.html
[nginx]: https://nginx.org
