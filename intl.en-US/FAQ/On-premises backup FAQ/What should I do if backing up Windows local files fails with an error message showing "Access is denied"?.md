# What should I do if backing up Windows local files fails with an error message showing "Access is denied"? {#concept_zdt_h1l_5fb .concept}

## Description {#section_f3z_l1l_5fb .section}

When you use a backup client to back up local Windows files, the backup fails, and the number of errors is displayed.

![](images/31898_en-US.png)

Click the number of errors next to the backup job to download a full report. The report contains error messages that indicate "Access is denied".

![](images/31899_en-US.png)

## Solution {#section_dlf_n1l_5fb .section}

This issue occurs when users in the SYSTEM group are not granted full access to failed files. To resolve this issue, grant the SYSTEM group full access to these failed files.

![](images/31901_en-US.png)

