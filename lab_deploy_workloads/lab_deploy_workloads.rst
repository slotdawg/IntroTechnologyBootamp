.. _lab_deploy_workloads:

-------------------------
Deploying Workloads Lab
-------------------------

Overview
++++++++

In addition to storage, VM creation, management, and monitoring can all be performed for Nutanix AHV directly through Prism.

.. note::

   Prism also offers native support for VM CRUD operations for Nutanix clusters running ESXi when the vCenter has been registered in Prism.

Deploying Workloads
+++++++++++++++++++

In the following exercise we'll walk through creating VM from  disk images.

Creating a Linux VM
...................

In this exercise you will create a CentOS VM from an existing, pre-installed disk image in the Image Service. It is common in many environments to have "template" style images of pre-installed operating systems. Similar to the previous exercise, the disk image has already been uploaded to the Image Service.

#. In **Prism Element > VM > Table**, click **+ Create VM**.

#. Fill out the following fields and click **Save**:

   - **Name** - *Initials*-Linux_VM
   - **Description** - (Optional) Description for your VM.
   - **vCPU(s)** - 1
   - **Number of Cores per vCPU** - 1
   - **Memory** - 2 GiB

   - Select **+ Add New Disk**
      - **Type** - DISK
      - **Operation** - Clone from Image Service
      - **Image** - CentOS7.qcow2
      - Select **Add**
      - **Boot Configuration**
      - Leave the default selected **Legacy Boot**

    *This will create a thin clone of the existing CentOS disk image*

   - Select **Add New NIC**
      - **VLAN Name** - Primary
      - Select **Add**

   .. figure:: images/deploy_workloads_03.png

#. Click **Save** to create the VM.

#. Select the VM, then click **Power On** from the list of action links (below the table) to turn on the VM.

   .. figure:: images/vm_power_on.png

#. **Launch the console** to see the VM being started.

Takeaways
+++++++++

- In this lab you saw how simple it is to deploy a VM from Disk Image.
- The Image Configuration tool allows you to have a catalog of available images to be used in VM deployments as needed and covering a broad format support which includes qcow, qcow2, vmdk, VHD, VHDx, RAW, and ISO.
