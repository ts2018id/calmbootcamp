.. _calm_enable:

------------
Calm: Enable
------------

Pendahuluan
+++++++++++

.. note::

  Review :ref:`calm_basics` sebelum melanjutkan Lab untuk membiasakan diri dengan Nutanix Calm user interface dan terminologinya. 

  Perkiraan waktu selesai dalam: **10 MINUTES**

Latihan ini kita akan meng-enable Nutanix Calm.

Enabling App Management
+++++++++++++++++++++++

Calm dibangun terintegrasi dengan Prism Central, sehingga tidak membutuhkan tambahan appliance atau konsol untuk manajemen. Sebelum dapat mengelola app dengan Calm, layanan ini harus di-enable.

.. note::

  Calm hanya dapat di-enable sekali per tiap Prism Central instance. Jika **Enable app management** menampilkan checkmark hijau itu artinya Calm sudah di-enable. Lanjutkan ke :ref:`calm_projects`.

#. Di **Prism Central**, klik **?** drop down menu, expand **New in Prism Central** dan pilih **Enable app management**.

#. Klik **Enable**.

.. figure:: images/510enable1.png

#. Pilih **Enable App Management** dan klik **Save**.

.. note:: Nutanix Calm memerlukan license terpisah yang dapat digunakan bersama license edisi Acropolis Starter, Pro, or Ultimate.

.. figure:: images/510enable2.png

#. Verifikasi bahwa Calm telah di-enable akan diberikan setelah kurang lebih 5-10 mennit.

.. figure:: images/510enable3.png

Menambah Active Directory
+++++++++++++++++++++++

Sementara kita menunggu Calm di-enable, kita akan menambah Active Diretory (AD) server. Untuk pemakaian basic, AD ini tidak diperlukan, namun jika ingin menggunakan Role Based Access Control, maka AD dibutuhkan.

#. Klik **Gear Icon** lalu klik **Authentication**.

.. figure:: images/510enable4.png

#. Di menu pop up, klik **New Directory**.

.. figure:: images/510enable5.png

#. Isi field yang kosong sesuai informasi AD dan klik **Save**:

- **Directory Type** - Active Directory
- **Name** - NTNXLAB
- **Domain** - ntnxlab.local
- **Directory URL** - ldaps://*<DC-VM-IP>*
- **Search Type** - Non Recursive
- **Username** - Administrator@ntnxlab.local
- **Password** - nutanix/4u

.. figure:: images/510enable6.png

#. Refresh browser dann pilih **Calm** dari navigation bar.  Jika Calm masih berproses, tunggu beberapa menit dan coba lagi.

.. figure:: images/510enable7.png
