## Role Name: Nagios

Ansible role which allows you to install Nagios on Debian systems.

## Requirements

Debian 9, 10, 11 and nagios prerequisites mentioned in role variables.

## Role Variables

Version of Nagios Core.
````yaml
nagios_version: 4.4.6
````

Version of Nagios plugins.
````yaml
nagios_plugins_version: 2.3.3
````

Nagios prerequisites needed before installation.
````yaml
nagios_prerequisites: [autoconf, gcc, libc6, make, wget, unzip, apache2, apache2-utils, php, libgd-dev, libmcrypt-dev, libssl-dev, bc, gawk, dc, build-essential, snmp, libnet-snmp-perl, gettext]
````
URL path of Nagios Core.
````yaml
nagios_download_url: "https://github.com/NagiosEnterprises/nagioscore/archive/nagios-{{ nagios_version }}.tar.gz"
````

Nagios Core download location, default in /tmp location. 
````yaml
nagios_download_path: "/tmp/nagioscore-nagios-{{ nagios_version }}"
````

Nagios plugins download location.
````yaml
nagios_plugins_download_path: "/tmp/nagios-plugins-release-{{ nagios_plugins_version }}"
````
               
Nagios plugins URL path.
````yaml
nagios_plugins_download_url: "https://github.com/nagios-plugins/nagios-plugins/archive/release-{{ nagios_plugins_version }}.tar.gz" 
````

Nagios user account and password to web GUI.
````yaml
nagios_username: nagiosadmin
nagios_password: nagios
````


## Dependencies

None.

## Example Playbook

````yaml
    - hosts: all
      become: yes
      roles:
         - nagios
````

## License

MIT

## Author Information

Role created by Piotr Kurylak.