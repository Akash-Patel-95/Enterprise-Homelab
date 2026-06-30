
June 29, 2026

Created IT - Software deployment GPO under - Forest: homelab.local > domains > homelab.local > Patelsfam > Workstations > IT
<img width="1089" height="495" alt="image" src="https://github.com/user-attachments/assets/8f224bdd-612d-4c43-99bf-495fb266ca69" />

Edit the policy
<img width="1178" height="654" alt="image" src="https://github.com/user-attachments/assets/37e594ca-a488-45d3-8dfe-2434c671fccf" />
<img width="1187" height="652" alt="image" src="https://github.com/user-attachments/assets/be65a7b7-54cd-4d5b-bf5e-19839a248026" />

7-zip package added - WRONG PATH - Troubleshooting
<img width="1116" height="382" alt="image" src="https://github.com/user-attachments/assets/636dfbec-0f30-44fe-959a-aae1b4f85b84" />

7-zip package added - corrected path
<img width="1117" height="376" alt="image" src="https://github.com/user-attachments/assets/e8fde85a-680e-41b0-9a69-9a4e534d92ab" />


On win11-02 workstation > ran gpupdate /force
<img width="1386" height="449" alt="image" src="https://github.com/user-attachments/assets/9428001e-195e-48eb-9ed9-0c33ad510a4f" />

reboot the workstation
Installed 7-Zip
<img width="884" height="751" alt="image" src="https://github.com/user-attachments/assets/1ed55920-e51b-430f-9f6d-f11d138ada46" />



Group Policy Software Installation
Issue

Software assigned through Group Policy did not install on domain-joined Windows clients after reboot.

Symptoms
Group Policy applied successfully.
Software package appeared under Software Installation.
gpresult confirmed the GPO was applied.
Software never appeared in Installed Apps.
Root Cause

The MSI package was added using a local file system path:

C:\Shares\Software\7-Zip\7z2602-x64.msi

Windows clients cannot access a server's local drive during computer startup.

Resolution

Removed the package from the GPO and recreated it using the UNC network path:

\\25-SRV-OH-01\Software\7-Zip\7z2602-x64.msi

Updated Group Policy and restarted the workstation.

The software installed successfully during computer startup.

Lesson Learned

Always use UNC network paths when deploying software through Group Policy.
