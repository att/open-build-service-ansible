open-build-service
==================

Installs and configures the [Open Build Service (OBS)](https://openbuildservice.org/).

Requirements
------------

This role is written for OpenSUSE, and is currently tested on OpenSUSE Leap 15.1. It makes use of the `zypper` and `zypper_repository` modules, so you need to install the `python-xml` package. Due to the use of the firewalld module, you must use Python 3 for your `ansible_python_interpreter`.

Role Variables
--------------

### obs_version

The version of OBS to install. Only 2.10 is tested. The default is 2.10.

### obs_opensuse_version

The version of OpenSUSE OBS is being installed on. The default is 15.1.

### obs_fqdn

The fully qualified domain name for this OBS instance. The default is "obs.internal".

### obs_cert_domains

The domains to use when generating a self-signed certificate. The default is ["{{ obs_fqdn }}", "obs", "localhost"].

### obs_cert_path

Path to a certificate for the web server to use. Disables self-signed certificate generation when set.

### obs_key_path

Path to a key for the web server to use.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Development
-----------

The easiest way to test your changes is using [Vagrant](https://www.vagrantup.com/). Once you have installed Vagrant, you can create and provision a VM like this:

    $ cd open-build-service
    $ vagrant up

After making changes, you can run Ansible again like this:

    $ vagrant provision

Once you're finished, you can destroy the VM like this:

    $ vagrant destroy

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
