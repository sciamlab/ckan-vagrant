#
# OCT 26, 2017 --> this repo has been relocated here https://gitlab.com/sciamlab/ckan-vagrant
#
# SciamLab standard ckan-vagrant

This is the vagrant setup and provisioning for a full fledged CKAN 2.7.3 setup on VirtualBox standard Ubuntu 16.xx LTS (Xenial) using recent software packages like PostgreSQL 10, PostGIS 2.4.3, SOLR 7.2.1 and many other goodies. The CKAN setup is finally deployed on an Apache2 using mod_wsgi.

This project is keept regurarly updated with recent CKAN version and related packages and tooling so that you can ramp-up quickly your dev environt without the hassle of resolving installation conflicts that tipically arise when playing with new stuff  

With the CKAN setup are also bootstrapped and configured the following CKAN extensions and plugins:
  * [DataStore](http://docs.ckan.org/en/latest/maintaining/datastore.html)
  * [DataPusher](http://docs.ckan.org/projects/datapusher/en/latest/)
  * [FileStore](http://docs.ckan.org/en/latest/maintaining/filestore.html)
  * [Resource Proxy](http://docs.ckan.org/en/latest/maintaining/data-viewer.html#resource-proxy)
  * [Spatial Extension](https://github.com/ckan/ckanext-spatial) 

## Quickstart

1. **Prerequisites**
    * install [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
    * install [Vagrant](https://www.vagrantup.com/intro/getting-started/install.html)

    The setup has been tested with recent version of Vagrant (2.0.2 e 2.0.3)
    please ensure your Virtualbox version is a supported one by Vagrant. These include the recent 5.1 version but not yet the latest 5.2.
    In case you want use VirtualBox 5.2 with Vagrant you can add support for it following [this hotfix](https://github.com/hashicorp/vagrant/issues/9090#issuecomment-338084000)

2. **Clone this repo**

	```shell
	$ git clone git@gitlab.com:sciamlab/ckan-vagrant.git
	```
3. **Create the running VM**

	```shell
	$ cd ckan-vagrant
	$ vagrant up
	```
	> In case your host environment doesn't have a network adapter named `eth1` the vagrant will ask you to choose one from those available. You can choose either Ethernet or WiFI devices


## Setup Details

* **Virtualbox VM**

	| **Component**       | **Version details**                                                                                          |
	|---------------------|--------------------------------------------------------------------------------------------------------------|
	| **OS**              | Ubuntu 16.04.3 LTS based on [Vagrant ubuntu/xenial64 box](https://atlas.hashicorp.com/ubuntu/boxes/xenial64) | 
	| **CPU Cores**       | 2 CPU Cores                                                                                                  |
	| **RAM**             | 2 Gb RAM                                                                                                     |


* **Installed packages**

	| **Component**    | **Version Details**                                                 |
	|------------------|---------------------------------------------------------------------|
	| **CKAN**         | [CKAN 2.7.2](https://github.com/ckan/ckan)                          |
	| **PostgreSQL**   | PostgresSQL 10 - PostGIS 2.4.3 r16312 - PSQL      		              |
	| **SOLR**         | [Apache SOLR 7.2.1](https://lucene.apache.org/solr/)                |
	| **Python 2**     | Python 2.7.12                                                       |
	| **Java**         | [OpenJDK 8](http://openjdk.java.net/)                               |
	| **Apache HTTP2** | Apache2 HTTPD 2.4.18                                                |
	| **mod_wsgi**     | [mod_wsgi 4.3.0](https://github.com/GrahamDumpleton/mod_wsgi)       |


## What's next
You may want configure email notification from your CKAN setup. In such case you can install an email server like [postfix]() and then [follow the instruction](http://docs.ckan.org/en/latest/maintaining/email-notifications.html) on the standard CKAN documentation

## Questions, Issues ?
features Feel free to [contact us](https://www.sciamlab.com/contact) or [create a new issue](issues/new) on this repository. We'll do our best to try and help!
If you want additional tools and packages are added and maintained updated here just add an issue for it !

## License
Apache License Version 2.0. See [LICENSE](LICENSE) for more details
