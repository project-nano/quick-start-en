.. faq .

.. contents:: Chapters
  :depth: 2

---------
FAQ
---------

Install requirements for Nano?
===================================

- Virtualization enabled X86 servers, or nested virtualization enabled virtual machines
- 2 cores/4 GB memory/50 GB disk/1 network interface
- CentOS 7.6(1810) Minimal
- Operation system installed with network ready

Can Nano be installed on a virtual machine?
==================================================

All products enable nesting virtualization is possible in theoretically. Tested products:

- VMware Station, test OK with Intell VT-x/AMD-V enabled
- VMware ESXi, test OK with Promiscuous Mode
- VirtualBox, test fail

Can Nano install on a public cloud like AWS?
================================================

No, most public cloud platforms do not allow virtualization.

Network/SSH disconnected when installing Nano
==================================================

The installer will configure network bridge and restart network service during installation, which does not affect the network connection for most Dell series servers and VMware instances.

However, it is true that some servers may cause network disconnection due to network drivers, which should install using the server's IPMI or similar remote administration interface instead of SSH.

Prompt "no default route available" when Installer or Cell starts
=====================================================================

Nano requires a default route configured to work, manually configure a new one and restarted.
Assuming that the default gateway in the network is 192.168.1.1, execute below command.

::

  $ip route add default via 192.168.1.1


Prompt "query timeout" when starting Cell
=============================================

The Cell requires a running Core process to complete self-discovery and networking. Check if the Core module and network are running correctly or the domain parameters are identical to Core's configure.

All instances and images absent after upgrading 0.9.1
=============================================================

Since the new version can only view the instances and images you created, execute the following instructions to modify the ownership of resources and restart the modules, otherwise you will not be able to see your instances and images.
Take the user 'nano' and group 'admin' as an example:

::

  Update ownership of images in the Core module
  $sed -i 's/\"owner\": \"admin\"/\"owner\": \"nano\"/' /opt/nano/core/data/image.data
  $sed -i 's/\"group\": \"manager\"/\"group\": \"admin\"/' /opt/nano/core/data/image.data

  Update ownership of instances in the Cell module
  $sed -i 's/\"user\": \"admin\"/\"user\": \"nano\"/' /opt/nano/cell/data/instance.data
  $sed -i 's/\"group\": \"manager\"/\"group\": \"admin\"/' /opt/nano/cell/data/instance.data

No "log" or "visibility" menu available after upgrading
===========================================================

Check on the "log" or "visibility" menu for the corresponding role in the permission management, and log in again.
