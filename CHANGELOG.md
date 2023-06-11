# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.3.0] 2023-06-11
* Bump python version to 3.11 by default
* Support RHEL 9
* Does not support older version of RHEL under 8.8 (due of python version)

## [2.2.0] 2021-06-03
* Fix, change package installs to ensure_packages(), so class can work with other manifests without resource dupes. [Fixes #11](https://github.com/anderssh/ash-netbox/issues/11)
* Also fixed several tests that were failing.
* Also fixed some dependency issues where if you manage redis or database elsewhere, the catalog will not compile. [Fixes #10](https://github.com/anderssh/ash-netbox/issues/10)   
Thank you to github user [```lukebigum```](https://github.com/lukebigum) for submitting PRs

## [2.1.0] 2020-12-17
* Feature, add possibility to configure encoding and locale on postgreSQL database, [as proposed here](https://github.com/anderssh/ash-netbox/issues/8)
* Fix, The 'webhooks' REDIS configuration section has been renamed to 'tasks', [Fixes #9](https://github.com/anderssh/ash-netbox/issues/9)
* Bump default version to 2.10.1

## [2.0.1] 2020-06-09
* Bugfix, add `refresh_only` to the exec that changes owner on archive, fixes that corrective change is applied at every puppet run

## [2.0.0] 2020-06-01
* Add notify arrow and move "install local requirements"
* Use root to unarchive, so you can put the netbox application a place where the netbox user doesn't have wright access.
* Use version 2.8.5 as default.

## [1.1.1] 2020-05-26
* Bugfix, some `VIRTUAL_ENV`s were hard coded. Use the `$venv_dir` variable instead

## [1.1.0] 2020-05-07

* Don't enforce creation and letting netbox own `$install_root`
* Change description of `$install_root`
* Clean up code
* Add correct documentation of the `$metrics_enabled` parameter

## [1.0.1] 2020-04-29

* Bugfix, there was a rouge space in `allowed_hosts` in the config template.

## [1.0.0] 2020-04-08

* Add support for all the date and time parameters
* Use version 2.7.11 as default. 
* Add more in the limitations section
* First major version
* Formatting, pdk updates, structuring


## [0.2.1] 2020-03-31

* Handle `ADMINS` in the config with the the `admins` array of hashes
* Handle debug option
* Handle enforce_global_unique option
* Handle exempt_view_permissions option
* Handle the metrics_enabled option
* Handle the prefer_ipv4 option
* Add validate command to validate python
* Add Napalm support (no Napalm arguments yet)
* Add possibility to download django-storage. Can not be configured yet
* Add way to install Netbox with this module without access internet.

## [0.1.0] 2020-03-25

* Initial release.
* Download, install and start Netbox, with optionally also handling PostgreSQL and redis.
* Most important settings can be configured, but plenty are missing.
* Supports EL8 and nothing else right now.