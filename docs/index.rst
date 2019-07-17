.. index .

======================
Nano Quick Guide
======================

Notes
======

This manual provides an overview of the basic concepts about the Nano platform, also demonstrates the main features in version 1.0.

Welcome to the official website https://nanos.cloud/ for more information.

Introduction
======

Nano是基于CentOS/KVM虚拟化技术，使用服务器集群构建计算资源池并提供云主机实例管理服务的新一代IaaS（架构即服务）软件平台。

Nano最大可能采用智能化和自动化手段替代繁琐易出错的手工操作，在简单易用的基础上，提供强大而稳定的云管理平台，产品，在解放运维人员的同时，提高集群的资源利用率、可用性和可靠性。

Nano基于Go语言开发，在极低的资源占用下提供强大而稳定的服务，同时避免Openstack等传统云平台需要大量外部组件依赖，维护复杂并且稳定性差的问题。所有模块均编译为独立运行的二进制包，模块升级时直接替换即可，无需考虑复杂的外部依赖，极大降低了维护难度和工作量。

对于支持Intel VT-d或者AMD-v的普通x86服务器，管理员只需要下载并安装Nano部署包，即可在三分钟内将其转换为云管理平台，并且开始创建云主机实例。

Nano自带对用户友好的图形化管理界面，能够实现开箱即用；Nano也同时提供对机器友好的完整REST API调用接口，可以方便地集成到现有产品或者自动化运维脚本。

Nano使用MIT许可，无论自用、修改或者商用都无限制

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
- **Broswer** : Chrome/Firefox
- **Multilingual** : English/Chinese


章节
-------

.. toctree::
   :maxdepth: 2

   concept
   deployment
   instance
   platform
   faq
   community
