# Discover Unnecessary Ports
Use Nmap to discover unnecessary open ports on ACIDM01 and then close those ports using the Windows Defender Firewall
## Learning Outcome ##
- Discover unnecessary open ports
- Close unnecessary open ports

## Devices ##
- ACIDC01 - Windows Server 2022 - Domain Controller
- ACIDM01 - Windows Server 2022 - Domain Member Server
- ACIKALI - Kali Purple 2023.1 - Stand-alone Linux Workstation

## Let's Start ##
- Connect to ACIDM01 and click the Send Ctrl+Alt+Delete button in the top right of the VM window.
- Then login with the password of 
   - Passw0rd
- Click the Start charm
   - select XAMPP > XAMPP Control Panel
- In the XAMPP Control Panel window, select Start for the Apache server
- In the XAMPP Control Panel window, select Start for the MySQL server
   - Close the XAMPP Control Panel
- Connect to ACIKALI
  - On the Desktop Toolbar, select Terminal Emulator
- In the Terminal window, type the following and press Enter
  - nmap -Pn 192.168.0.2
<img width="1075" height="853" alt="image" src="https://github.com/user-attachments/assets/060b4c24-75f1-40b0-8ce2-14d6377a0618" />

- Type the following and press Enter
  - nmap -Pn -A -p 80,443,3306 192.168.0.2
<img width="1083" height="473" alt="image" src="https://github.com/user-attachments/assets/b8eb5c7a-10a0-41d4-9cbe-24391d79f9cc" />

- ### Notice that Apache 2.4.56 is running on ports 80 and 443 and that a MariaDB is running on port 3306. These ports are unnecessarily open and should be closed. ###
