<h1>Disabling Windows Firewall and Installing MS SQL Server</h1>
This tutorial outlines disabling Windows Firewall on the windows virtual machine and installing MS SQL Server.

<h2>Environments and Technologies Used</h2>

- <b>Microsoft Azure</b> 
- <b>Remote Desktop</b>
- <b>Windows Firewall</b>
- <b>MS SQL Server</b>

<h2>Operating Systems</h2>

- <b>Windows 10</b>


<h2>Installation Steps</h2>

![rdp](https://github.com/user-attachments/assets/216fa4d2-0de1-4189-85ae-ea9ea1c6b5d2)
- <b>Open Remote Desktop Connection from your host computer</b>
- <b>Connect to your windows virtual machine using its IP address</b> 

![firewall](https://github.com/user-attachments/assets/61f1b9fb-6389-4abd-a542-0a7ae7d44636)
- <b>From your Windows virtual machine, open Windows Firewall and turn off domain, public and private profiles</b>
- <b>This will allow our Windows virtual machine to be discovered and accessed by bad actors across the internet</b>

![ping](https://github.com/user-attachments/assets/16047d59-32b7-4a1f-b412-971c15a7c365)
- <b>Open the command prompt from your host computer and ping your Windows virtual machine using its IP address</b>

![MS SQL](https://github.com/user-attachments/assets/f9621218-29d0-490e-814b-28480abaf38f)
- <b>Install MS SQL Server Evaluation: https://www.microsoft.com/en-us/evalcenter/evaluate-sql-server-2019</b>
- <b>Download the EXE file</b>

![setup](https://github.com/user-attachments/assets/3b2ac35c-a5c2-479c-ae00-e49fe663ab5c)
- <b>Click Setup</b>

![installation](https://github.com/user-attachments/assets/78cd8c7d-4d7e-4ab4-bfef-55be8b46a672)
- <b>Click Installation and "New SQL Server stand-alone installation"</b>
- <b>Username: sa</b>
- <b>Password: Cyberlab1234</b>
- <b>Add Current User</b>

![ssms](https://github.com/user-attachments/assets/7fa263b0-5675-4889-ac44-d99993e8f1ea)
- <b>Dowload SQL Server Management Studio: https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16</b>

![image](https://github.com/user-attachments/assets/ca24eb25-dfb5-4e62-8ccb-6263df228900)
- <b>Open Registry Editor</b>
- <b>Navigate to this file path: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\EventLog\Security</b>
- <b>Add NETWORK_SERVICE</b>
- <b>Allow full control and read</b>

![image](https://github.com/user-attachments/assets/00974825-fc7d-46be-bc57-355ef07128f0)
- <b>Open and log in to SQL Server Management Studio</b>
- <b>Right click windows-vm, click properties, click security, check both failed and successful logins in the Login auditing</b>

![image](https://github.com/user-attachments/assets/c98b116e-89d9-4ecf-b432-544a056dd745)
- <b>Perform a failed login attempt</b>

![image](https://github.com/user-attachments/assets/8890dae0-0ca5-45bc-a3aa-e2c40fa7ea8b)
- <b>Open Event Viewer, Window Logs, and then Application to view the recorded SQL Server login attempts</b>

![image](https://github.com/user-attachments/assets/cbc8d9ff-b675-447a-8993-3313084fc923)
- <b>Ping linux-vm using its IP address</b>
- <b> Log in to linux-vm using ssh</b>






