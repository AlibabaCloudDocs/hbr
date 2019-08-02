# FAQ about local virtual machines {#concept_p1l_z55_jgb .concept}

## Why do I fail to import an OVA template for a virtual machine client? {#section_eym_bv5_jgb .section}

You can only deploy an OVA template on a web client that runs vCenter Server 5.5, 6.0, or 6.5. If an error occurs when you import an OVA template, you need to check that the version of vCenter Server is supported by Hybrid Backup Recovery \(HBR\).

## Why do I fail to add a vCenter Server instance to HBR when the IP address, account, and password are correct? {#section_bgz_h1c_rfb .section}

The password of the vCenter account may contain special characters. We recommend that you create a vCenter account dedicated for backup, and ensure that the password of the account does not contain any special characters.

