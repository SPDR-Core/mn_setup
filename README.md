# How to setup Spider Masternode  
- [How to setup Spider Masternode](#how-to-setup-spider-masternode)  
  * [VPS initial setup](#vps-initial-setup)  
        * [Requirements](#requirements)  
        * [1. Download Bitvise SSH Client](#1-download-bitvise-ssh-client)  
        * [2. Log into the VPS with **root**](#2-log-into-the-vps-with-root)  
        * [3. Git Installation](#3-git-installation)  
        * [4. Clone MN setup script](#4-clone-mn-setup-script)  
        * [5. Start Mn setup script](#5-start-mn-setup-script)  
  * [Setup QT wallet](#setup-qt-wallet)  
        * [1. Create new receiving address and copy it](#1-create-new-receiving-address-and-copy-it)  
        * [2. Send 7000 SPDR to copied address](#2-send-7000-spdr-to-copied-address)  
        * [3. Wait at least 10 confirms of transaction](#3-wait-at-least-10-confirms-of-transaction)  
        * [4. Generate new key for MN](#4-open-debug-console-tools-debug-console-and-generate-new-key-for-mn)  
        * [5. Get MN output](#5-get-mn-output)  
        * [6. Open masternode configuration file](#6-open-masternode-configuration-file)  
        * [7. Edit the masternode configuration file and save it](#7-edit-the-masternode-configuration-file-and-save-it)  
        * [8. Restart QT wallet](#8-restart-qt-wallet)  
        * [9. Copy MN key to VPS console](#9-copy-mn-key-to-vps-console-window-and-pres-enter)  
        * [10. Wait for VPS sync with blockchain](#10-wait-for-vps-sync-with-blockchain)  
        * [11. Start MN in QT wallet console](#11-start-mn-in-qt-wallet-console)  
## VPS initial setup

##### Requirements
- Ubuntu v16.04.x VPS with 1 CPU / 1gb MEM (recommend 2gb)
- [Bitvise SSH Client] 
***  
##### 1. Download Bitvise SSH Client  
[![Download Bitvise](https://i.imgur.com/TICk0sK.png)](https://www.bitvise.com/download-area)  

***
##### 2. Log into the VPS with **root**  
[![Vps](https://i.imgur.com/j89ogDO.png)](https://www.bitvise.com/download-area)
***
##### 3. Git Installation:  
- ```sudo apt-get install -y git-core```  

[![Git](https://i.imgur.com/LsXZwgW.png)]()
***
##### 4. Clone MN setup script: 
- ```git clone https://github.com/SPDR-Core/mn_setup```  

[![Script1](https://i.imgur.com/P32LqNU.png)]()
***
##### 5. Start Mn setup script: 
- ```cd mn_setup && chmod +x mn_spdr.sh && ./mn_spdr.sh```  

[![Script2](https://i.imgur.com/453wrsS.png)]()  
***
**Now you need to wait some time, while script preparing the VPS to setup**  
This means your UPU is ready to start:[![Download Bitvise](https://i.imgur.com/2CxDbTd.png)]() 
**Don't close this window!** 
***
## Setup QT wallet
##### 1. Create new receiving address and copy it
[![QT1](https://i.imgur.com/ymccgSG.png)]() 
[![QT2](https://i.imgur.com/fz5fJFc.png)]()
***
##### 2. Send 7000 SPDR to copied address
[![QT3](https://i.imgur.com/L7GOhjI.png)]() 
***
##### 3. Wait at least 10 confirms of transaction
[![QT4](https://i.imgur.com/oVQfXMg.png)]()
***
##### 4. Open *Debug console* (Tools->Debug console) and generate new key for MN:  
- ```masternode genkey```  

[![QT5](https://i.imgur.com/ZLLNSec.png)]()
***
##### 5. Get MN output:
- ```masternode outputs```  

[![QT6](https://i.imgur.com/n0goggM.png)]()
***
##### 6. Open masternode configuration file
- [![QT7](https://i.imgur.com/WUwLlAG.png)]()
***
##### 7. Edit the masternode configuration file and save it
- ```mn1 VPS_IP:53617 masternode_genkey masternode_output output_index```:  

[![QT8](https://i.imgur.com/cCOz2cF.png)]()
***
##### 8. Restart QT wallet  
- **it's important**
***
##### 9. Copy MN key to VPS console window and pres "Enter"
- on VPS window right-click to paste
[![QT9](https://i.imgur.com/IfkfYMg.png)]()  

if you see this, you are on the right track:
[![QT10](https://i.imgur.com/U7x45BY.png)]()
***
##### 10. Wait for VPS sync with blockchain
- to check VPS sync, type: ```spdr-cli getinfo``` if "blocks" coincides with the last block in the [Explorer], your VPS is synced!
[![QT11](https://i.imgur.com/tVcawGe.png)]()
***
##### 11. Start MN in QT wallet console:
- ```masternode start-alias mn1```  

[![QT12](https://i.imgur.com/ZxR5Yef.png)]()  

**Сongratulations you did it!**

[Bitvise SSH Client]: <https://www.bitvise.com/download-area>
[Explorer]: <http://explorer.spidervps.net>
