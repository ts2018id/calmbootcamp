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
  :caption: Optional Labs
  :name: _optional_labs
  :hidden:

  flow_assign_categories_in_calm/flow_assign_categories_in_calm
  
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


Detail Environment
+++++++++++++++++++

Nutanix Workshops dirancang untuk lingkungan Nutanix Hosted POC, dimana semua images, network dan VMs yang diperlukan untuk menyelesaikan latihan akan disediakan.

Informasi Cluster Hosted POC Reservation: **PHX-POC021** (NX-3060).

Reservation ID: 78995

- Start Date: 2019-11-27 20:00
- Stop Date: 2019-12-04 20:00
- Timezone: Singapore

Networking
..........

Informasi Hosted POC clusters network:

- **Cluster Name** - POC021
- **Subnet Mask** - 255.255.255.128
- **Gateway** - 10.42.211
- **Nameserver IP** - 10.42.196.10

**Informasi Secondary Network**

- **Secondary VLAN**: 211
- **Secondary Subnet**: 255.255.255.128
- **Secondary Gateway**: 10.42.21.129
- **Secondary IP Range**: 10.42.21.132-254

**Cluster IP: https://10.42.21.37:9440/console/#login**

* Node: A CVM IP: 10.42.21.29 Hypervisor IP: 10.42.21.25 IPMI IP: 10.42.21.33
* Node: B CVM IP: 10.42.21.30 Hypervisor IP: 10.42.21.26 IPMI IP: 10.42.21.34
* Node: C CVM IP: 10.42.21.31 Hypervisor IP: 10.42.21.27 IPMI IP: 10.42.21.35
* Node: D CVM IP: 10.42.21.32 Hypervisor IP: 10.42.21.28 IPMI IP: 10.42.21.36

**Login Credentials**

* Prism UI Credentials: admin/nut4nixP@ssw0rd
* CVM Credentials: nutanix/nut4nixP@ssw0rd
* Prism Central IP: 10.42.21.39 [10.42.21.39]
* Prism Central Credentials: admin / nut4nixP@ssw0rd
* AHV Host Credentials: root / nut4nixP@ssw0rd

Tiap cluster memiliki dedicated domain controller VM yang menyediakan layanan active directory untuk environment ini.
Domain ini memiliki users dan groups sebagai berikut:

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



Akses Lab
+++++++++++++

- User Accounts: *PHX-POC021-User01, PHX-POC021-User02 … PHX-POC021-User20*
- User Password: nut4nixP@ssw0rd

**Pulse Secure VPN Client**

1. Step ini tidak diperlukan jika sudah meng-install VPN Client  
2. login ke https://xlv-uswest1.nutanix.com atau https://xlv-useast1.nutanix.com menggunakan user credential yang sudah disediakan diatas.
3. Download dan install VPN client
4. Logout dari Web UI

Jalankan Pulse Secure VPN Client dan konfigure VPN sesuai informasi berikut: (Pilih akses melalui PHX atau RTP)

Akses PHX:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - PHX
- **Server URL** - xlv-uswest1.nutanix.com

Akses RTP:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - RTP
- **Server URL** - xlv-useast1.nutanix.com


Nutanix Version Info
++++++++++++++++++++

- **AHV Version** - AHV 20170830.279 (5.10+)
- **AOS Version** - 5.11
- **PC Version** - 5.11
