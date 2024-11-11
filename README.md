# China Unicome VN007+ Firmware/SuperAdmin Guide

## 1.Downgrade

You need to downgrade from your `current firmware` version to `1.10.10` and follow the sequence below:

[1.15.1](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.15.1_IDU_1.10.4_update.bin)
[1.12.8](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.12.8_usr_UN2020C_20220309_1.8.11_update.bin)
[1.12.5](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.12.5_IDU_1810_UN2020C_20220222_VN007_1.15UP_update.bin)
[1.10.2](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_IDU_1.10.2_usr_210821_update.pac)
[1.10.17](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.10.17_185_usr_20211012_update.pac)
[1.10.10](https://github.com/jymarkb/China-Unicome-VN007-/blob/main/Firmware/X21G_1.10.10_usr_UN2020C_20210918_1.8.5_update.pac)

Page.level=1

turn on adb shell

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

CHANGE IMEI:
AT+SPIMEI=0, "IMEI CODE HERE"
AT+SPIMEI?