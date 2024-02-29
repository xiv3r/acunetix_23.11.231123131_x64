<img width="1000" height="500" src="https://github.com/xiv3r/acunetix_23.11.231123131_x64/blob/main/logo/acunetix-logo.png">



# <h1 align="center"> Acunetix v23.11.231123131 </h1>

<p align="center"> Acunetix is an automated web application security testing tool that audits your web applications by checking for vulnerabilities like SQL Injection, Cross site scripting and other exploitable vulnerabilities. </p>


<br></br>

Updates: [Acunetix v24.1](https://github.com/xiv3r/Acunetix-Professional-v24.1)

### Setups:

    git clone https://github.com/xiv3r/acunetix_23.11.231123131_x64.git

    cd acunetix_23.11.231123131_x64

    wget https://github.com/xiv3r/acunetix_23.11.231123131_x64/releases/download/File/acunetix_23.11.231123131_x64.sh
   

- Before installing the tool, add to your hosts file `sudo nano /etc/hosts` and add the below file.
  ```
  127.0.0.1  erp.acunetix.com
  127.0.0.1  erp.acunetix.com.
  ::1  erp.acunetix.com
  ::1  erp.acunetix.com.

  192.178.49.174  telemetry.invicti.com
  192.178.49.174  telemetry.invicti.com.
  2607:f8b0:402a:80a::200e  telemetry.invicti.com
  2607:f8b0:402a:80a::200e  telemetry.invicti.com.
  ```
- Now lets Install acunetix:

      sudo bash acunetix_23.11.231123131_x64.sh

- Once installed let's stop its service with:

      sudo systemctl stop acunetix

- Replace wvsc file:

  ```
  mkdir -p /home/acunetix/.acunetix/v_231123131/scanner/wvsc
  sudo cp wvsc /home/acunetix/.acunetix/v_231123131/scanner/wvsc
  sudo chown acunetix:acunetix /home/acunetix/.acunetix/v_231123131/scanner/wvsc
  sudo chmod +x /home/acunetix/.acunetix/v_231123131/scanner/wvsc
  ```

- Adding the licenses:
  ```
  mkdir -p /home/acunetix/.acunetix/data/license/
  sudo cp license_info.json /home/acunetix/.acunetix/data/license/
  sudo cp wa_data.dat /home/acunetix/.acunetix/data/license/
  sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/license_info.json
  sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/wa_data.dat
  sudo chmod 444 /home/acunetix/.acunetix/data/license/license_info.json
  sudo chmod 444 /home/acunetix/.acunetix/data/license/wa_data.dat
  sudo chattr +i /home/acunetix/.acunetix/data/license/license_info.json
  sudo chattr +i /home/acunetix/.acunetix/data/license/wa_data.dat
  ```
  
7) Now let's restart acunetix:

       sudo systemctl start acunetix

8) Now go to Browser [https://localhost:3443](https://localhost:3443)
