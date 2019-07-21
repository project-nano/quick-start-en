.. concept .

.. contents:: Chapters
  :depth: 2

-----------
Concepts
-----------

A Nano platform currently consists of three modules: Core, Cell, and FrontEnd.

The Cell creates and manages virtual machines. The Core forms resource pools using multiple Cells, to schedule and allocates instances on demand; FrontEnd provides an HTML5 web portal based on the API service of the Core module.

Although all modules can install on a single server, it recommends that each module deploys on a separate server for better availability on a production system. As blow figure:



.. image:: images/1_1_nano_modules.png

the Nano has external and internal network communications.

The external communication includes the Web portal (TCP 5850 in default) and API service of the Core module(TCP 5870 in default), which can configure on your demand.

Internal communication includes the UDP packets between modules and HTTPS for data transmission. All ports are dynamically and automated allocated, no need to worry about them.

.. image:: images/1_2_communicate_overview.png


Communicate Domain
===============================

The modules of Nano can discover each other and automatically complete networking without any configuration.

The automatic discovery is implemented base on the multicast protocol. A communicate domain defined by a triple consist of a domain name, multicast address, and port (the default is < "Nano": 224.0.0.226:5599 >). Modules in the same domain can discover and communicate with each other.

If you need to configure multiple clusters within a LAN, you can assign different domain triples.

The valid multicast address range from "224.0.0.0" to "224.0.0.255". Refer to `Multicast address <https://en.wikipedia.org/wiki/Multicast_address>`_ for details.

As follow figure:

.. image:: images/1_3_domain_discovery.png

**the Core must start first as a stub module.** If the Core stops service or restarts, the module already started will automatically attempt to resume communication.

Resource Model
========================

A local Nano cluster forms an available zone, A zone contains multiple resource pools, each resource pool contains one or more Cell resource nodes.

A Cell can only belong to one pool. When creating or migrating an instance, the Core chooses an appropriate Cell according to the real-time load of each Cell in the specified pool.

.. image:: images/1_4_resource_model.png

There will be an empty default resource pool after system installed. **Do remember to add a Cell node to the resource pool before creating any instance.**

Images
==========

Nano has two kinds of images: disk image and media image.

The disk image represents the disk data of a virtual machine,  which can be used to fast clone batch of instances with the identical OS and software as the original one in a short time.

The media image represents a DVD data in ISO format, which can load into instance working as a physical CD for installing OS.

You can upload the pre-built image to the system to save the time of customization. Visit the official website to `Download <https://nanos.cloud/en-us/download.html>`_ the pre-built CentOS 7 image.

.. image:: images/1_5_images_overview.png
