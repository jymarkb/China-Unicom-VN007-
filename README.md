# China Unicom VN007+ Firmware/SuperAdmin Guide
This guide provides a step-by-step process for downgrading the China Unicom VN007+ and gaining superuser (admin) access; however, please be aware that your device may still be at risk of bricking, even if you follow the instructions carefully or choose not to follow them.

## **Downgrade**

You need to downgrade from your `current firmware` version to `1.10.10` and follow the sequence below:

**`Use an Ethernet cable, not WiFi, to flash the firmware.`**

[1.15.1](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.15.1_IDU_1.10.4_update.bin)
 `>>` [1.12.8](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.12.8_usr_UN2020C_20220309_1.8.11_update.bin)
 `>>` [1.12.5](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.12.5_IDU_1810_UN2020C_20220222_VN007_1.15UP_update.bin)
 `>>` [1.10.2](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_IDU_1.10.2_usr_210821_update.pac)
 `>>` [1.10.17](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.10.17_185_usr_20211012_update.pac)
 `>>` [1.10.10](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.10.10_usr_UN2020C_20210918_1.8.5_update.pac)

## Super Admin

1. Login on your device `http://192.168.0.1/`
2. Press F12 and type on the console `Page.level=1` <br /> ![image](https://github.com/user-attachments/assets/a3a07041-6b52-4627-9ff1-dd3f94115691)
3. Go to **Management** `>>` **System Setting** `>>` **ADB switch** and turn it on. <br /> ![image](https://github.com/user-attachments/assets/78f473b6-a410-4e9b-9d7b-0b2961de004f)
4. Open `CMD` and `CD` to [adb tools](https://github.com/jymarkb/China-Unicome-VN007-/tree/main/adb%20tools) path<br /> ![image](https://github.com/user-attachments/assets/14f680ea-6027-4370-8815-1983d545cbc7)
5. `Copy and paste` the code below, replacing `YOUR USERNAME HERE` and `YOUR PASSWORD HERE` with your own credentials:
```
adb connect 192.168.0.1:5555
adb -s 192.168.0.1:5555 shell
mdlcfg -f SYS_WEB_SUPER_PWD_RULE="1"
mdlcfg -a SYS_WEB_SUPER_PWD_RULE="1"
mdlcfg -f SYS_SUPER_LOGIN_NAME="YOUR USERNAME HERE"
mdlcfg -a SYS_SUPER_LOGIN_NAME="YOUR USERNAME HERE"
mdlcfg -f SYS_SUPER_LOGIN_PWD="YOUR PASSWORD HERE"
mdlcfg -a SYS_SUPER_LOGIN_PWD="YOUR PASSWORD HERE"
mdlcfg -c
exit
```
6. Restart the router.
7. Login `http://192.168.0.1/` using superadmin credential that you created.

## CHANGE IMEI
1. Login on your device `http://192.168.0.1/`
2. Go to **Management** `>>` **AT Command**
3. To check current IMEI `AT+SPIMEI?` then click send.
4. To change IMEI `AT+SPIMEI=0, "IMEI CODE HERE"`

