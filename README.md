Ansible Role: rpmfusion
==================
[![CI](https://github.com/egdoc/ansible-role-rpmfusion/actions/workflows/ci.yml/badge.svg)](https://github.com/egdoc/ansible-role-rpmfusion/actions/workflows/ci.yml)

Ansible role to enable the RPM Fusion repository

Role Variables
--------------
        rpmfusion_enable_nonfree_repo: false

Whether to enable the "nonfree" RPM Fusion repository. By default only the "free" one will be enabled.

        # Fedora
        rpmfusion_free_repo_rpm_url: https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-{{ ansible_facts.distribution_major_version }}.noarch.rpm
        rpmfusion_nonfree_repo_rpm_url: https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-{{ ansible_facts.distribution_major_version }}.noarch.rpm

        # RHEL/CentOS/Rockylinux
        rpmfusion_free_repo_rpm_url: https://mirrors.rpmfusion.org/free/el/rpmfusion-free-release-{{ ansible_facts.distribution_major_version }}.noarch.rpm
        rpmfusion_nonfree_repo_rpm_url: https://mirrors.rpmfusion.org/nonfree/el/rpmfusion-nonfree-release-{{ ansible_facts.distribution_major_version }}.noarch.rpm

The URL of the rpm packages which setup the free and nonfree RPM Fusion repositories. The defaults values changes depending if
you are using Fedora of RHEL (and clones).

        # Fedora
        rpmfusion_free_gpg_key_url: https://rpmfusion.org/keys?action=AttachFile&do=get&target=RPM-GPG-KEY-rpmfusion-free-fedora-2020
        rpmfusion_nonfree_gpg_key_url: https://rpmfusion.org/keys?action=AttachFile&do=get&target=RPM-GPG-KEY-rpmfusion-nonfree-fedora-2020

        # RHEL/CentOS/RockyLinux
        rpmfusion_free_gpg_key_url: https://rpmfusion.org/keys?action=AttachFile&do=get&target=RPM-GPG-KEY-rpmfusion-free-el-{{ ansible_facts.distribution_major_version }}
        rpmfusion_nonfree_gpg_key_url: https://rpmfusion.org/keys?action=AttachFile&do=get&target=RPM-GPG-KEY-rpmfusion-nonfree-el-{{ ansible_facts.distribution_major_version }}

The URL of the GPG keys used to sign packages in the RPM Fusion "free" and "nonfree" repositories.



Dependencies
------------
None

Example Playbook
----------------

    - hosts: all
      roles:
        - role: egdoc.rpmfusion

License
-------

GPLv2

Author Information
------------------
Created by Egidio Docile
