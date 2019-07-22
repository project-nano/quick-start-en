.. index .

======================
Nano Quick Guide
======================

Notes
=================

This manual provides an overview of the basic concepts about the Nano platform, also demonstrates the main features in version 1.0.

Welcome to the official website https://nanos.cloud/en-us/ for more information.

Author: Akumas (bokuore@github.com)

Git Repository: https://github.com/project-nano

Introduction
==================

Nano is an IaaS (Infrastructure as a Service) software based on CentOS and KVM virtualization technology, which manages virtual machines using server clusters as resource pools.

Nano is using automated methods to place human operates as many as possible, aiming to provide a powerful platform while keeping things simple and easy.

Nano is developed using Golang, build a fast and reliable service with a low footprint. All Nano modules compiled to standalone binaries, no dependent library required when deployed.

You can turn any server enable Intel VT-d or AMD-v technology into an IaaS platform, and begin deploying virtual machines in 3-minutes with a tiny Nano installer.

Nano comes with a user-friendly GUI out of the box, also provide a machine-friendly REST API which can easily integrate into current products or automated scripts.

Nano uses MIT license, which is free for modification, personal or commercial use.

Features
==============

- **Resource Pool** : Add, remove, enable and disable resource node/schedule instances/real-time resource usage&uptime monitor/multi-layer dashboard drill down
- **Storage backend support** : local disk storage/NFS shared storage
- **IPv4 Address pool** :  instance address management, multi-address range, gateway, DNS configure.
- **Cloud Instances** :

  - Lifecycle management: create/release/start/migrate/failover
  - Configuration management: modify guest name/core/memory, QoS(CPU/Disk IO/Bandwidth), extend and shrink disk, host template, reset system
  - Guest operating system: reset admin password, CPU/memory usage monitoring, automated disk format/mount, modify the hostname
  - Remote access: embedded HTML5 page, third-party VNC connection support, VNC connection encryption
  - Batch building: instance template build/clone/upload/download, batch creating and deleting
  - Data security: incremental snapshot creation/restore/manage
  - Media: ISO image upload/insert/eject
  - Network：address binding, recycling, and migration, gateway, DNS assignment

- **Platform management** : system initialization, user/user group/role manage, resource visibility, network discovery, start and stop modules, connection/running status detection, operate log
- **Tools** : Installer
- **Browser** : Chrome/Firefox
- **Multilingual** : English/Chinese


Chapters
----------------

.. toctree::
   :maxdepth: 2

   index
   concept
   deployment
   instance
   platform
   faq
   community
