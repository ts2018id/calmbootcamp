.. title:: Nutanix Calm Bootcamp

.. toctree::
  :maxdepth: 2
  :caption: Calm
  :name: _calm
  :hidden:

  what_is_calm/what_is_calm
  calm_enable/calm_enable
  calm_projects/calm_projects
  calm_linux/calm_linux
  calm_win/calm_win
  calm_day2/calm_day2
  calm_escript/calm_escript
  calm_marketplace/calm_marketplace

.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  appendix/glossary
  tools_vms/windows_tools_vm
  tools_vms/linux_tools_vm

.. _getting_started:

---------------
Pendahuluan
---------------

Selamat datang di sesi Hands on Lab Nutanix Calm @.NEXT on Tour Jakarta!. 

Setiap sesi berisi teori dan latihan hands-on di Nutanix Enterprise Cloud platform. 
Instruktur akan membantu sesi latihan dan menjawab pertanyaan yang ada.
Di akhir Bootcamp, perserta diharapkan dapat mengerti konsep dasar teknologi stack Nutanix Enterprise Cloud.

Level: Intermediate

Peserta diharapkan memiliki basic mengenai Nutanix

Agenda
++++++

- Nutanix Calm Labs
    - Calm: Enable
    - Calm: Projects
    - Calm: Linux 3-Tier Application
    - Calm: Windows 2-Tier Application
    - Calm: Day 2 Actions - Scaling Out/In
    - Calm: eScript
    - Calm: Marketplace


Akses Lab
+++++++++++++

- User Accounts: *PHX-POC021-User01, PHX-POC021-User02 … PHX-POC021-User20*
- User Password: nut4nixP@ssw0rd

**Pulse Secure VPN Client**

1. If client already installed skip to step 5 
2. login to https://xlv-uswest1.nutanix.com or https://xlv-useast1.nutanix.com using the supplied user credentials
3. Download and install client
4. Logout of the Web UI


Environment Details
+++++++++++++++++++

Nutanix Workshops are intended to be run in the Nutanix Hosted POC environment. Your cluster will be provisioned with all necessary images, networks, and VMs required to complete the exercises.

Your Reservation Information for **PHX-POC021** (NX-3060).

Reservation ID: 78995

- Start Date: 2019-11-27 20:00
- Stop Date: 2019-12-04 20:00
- Timezone: Singapore

Networking
..........

Hosted POC clusters follow a standard naming convention:

- **Cluster Name** - POC021
- **Subnet Mask** - 255.255.255.128
- **Gateway** - 10.42.211
- **Nameserver IP** - 10.42.196.10

- Secondary VLAN: 211
- Secondary Subnet: 255.255.255.128
- Secondary Gateway: 10.42.21.129
- Secondary IP Range: 10.42.21.132-254

**Cluster IP: https://10.42.21.37:9440/console/#login**

* Position: A CVM IP: 10.42.21.29 Hypervisor IP: 10.42.21.25 IPMI IP: 10.42.21.33
* Position: B CVM IP: 10.42.21.30 Hypervisor IP: 10.42.21.26 IPMI IP: 10.42.21.34
* Position: C CVM IP: 10.42.21.31 Hypervisor IP: 10.42.21.27 IPMI IP: 10.42.21.35
* Position: D CVM IP: 10.42.21.32 Hypervisor IP: 10.42.21.28 IPMI IP: 10.42.21.36

**Login Credentials**

* Prism UI Credentials: admin/nut4nixP@ssw0rd
* CVM Credentials: nutanix/nut4nixP@ssw0rd
* Prism Central IP: 10.42.21.39 [10.42.21.39]
* Prism Central Credentials: admin / nut4nixP@ssw0rd
* AHV Host Credentials: root / nut4nixP@ssw0rd


Throughout the Workshop there are multiple instances where you will need to substitute *XYZ* with the correct octet for your subnet, for example:

.. list-table::
  :widths: 25 75
  :header-rows: 1

  * - IP Address
    - Description
  * - 10.21.\ *XYZ*\ .37
    - Nutanix Cluster Virtual IP
  * - 10.21.\ *XYZ*\ .39
    - **PC** VM IP, Prism Central
  * - 10.21.\ *XYZ*\ .40
    - **DC** VM IP, NTNXLAB.local Domain Controller

Each cluster is configured with 2 VLANs which can be used for VMs:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1

  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Primary
    - 10.21.\ *XYZ*\ .1/25
    - 0
    - 10.21.\ *XYZ*\ .50-10.21.\ *XYZ*\ .124
  * - Secondary
    - 10.21.\ *XYZ*\ .129/25
    - *XYZ1*
    - 10.21.\ *XYZ*\ .132-10.21.\ *XYZ*\ .253

Credentials
...........

.. note::

  The *<Cluster Password>* is unique to each cluster and will be provided by the leader of the Workshop.

.. list-table::
  :widths: 25 35 40
  :header-rows: 1

  * - Credential
    - Username
    - Password
  * - Prism Element
    - admin
    - *<Cluster Password>*
  * - Prism Central
    - admin
    - *<Cluster Password>*
  * - Controller VM
    - nutanix
    - *<Cluster Password>*
  * - Prism Central VM
    - nutanix
    - *<Cluster Password>*

Each cluster has a dedicated domain controller VM, **DC**, responsible for providing AD services for the **NTNXLAB.local** domain. The domain is populated with the following Users and Groups:

.. list-table::
  :widths: 25 35 40
  :header-rows: 1

  * - Group
    - Username(s)
    - Password
  * - Administrators
    - Administrator
    - nutanix/4u
  * - SSP Admins
    - adminuser01-adminuser25
    - nutanix/4u
  * - SSP Developers
    - devuser01-devuser25
    - nutanix/4u
  * - SSP Power Users
    - poweruser01-poweruser25
    - nutanix/4u
  * - SSP Basic Users
    - basicuser01-basicuser25
    - nutanix/4u

Access Instructions
+++++++++++++++++++

The Nutanix Hosted POC environment can be accessed a number of different ways:

Parallels VDI
.................

Login to: https://xld-uswest1.nutanix.com (for PHX) or https://xld-useast1.nutanix.com (for RTP)

**Nutanix Employees** - Use your NUTANIXDC credentials
**Non-Employees** - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*

Pulse Secure VPN
..........................

To download the client: login to https://xlv-uswest1.nutanix.com or https://xlv-useast1.nutanix.com - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*

Download and install the client.

In Pulse Secure Client, **Add** a connection:

For PHX:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - PHX
- **Server URL** - xlv-uswest1.nutanix.com

For RTP:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - RTP
- **Server URL** - xlv-useast1.nutanix.com


Nutanix Version Info
++++++++++++++++++++

- **AHV Version** - AHV 20170830.279 (5.10+)
- **AOS Version** - 5.11
- **PC Version** - 5.11
