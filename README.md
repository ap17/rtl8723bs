rtl8723bs driver
v5.2.17.1_26955.20180307_COEX20180201-6f52

origin : https://github.com/thirdyouth/rtl8723bs

Currently (march 2020) used by me on Xunlong Orange OPi-Prime with Linux 5.6, Debian 10.
Works great both in access point mode and in infrastructure mode.

This driver must be built in "in-tree" mode.
1. put driver sources to ".../drivers/net/wireless/realtek/rtl8723bs"
2. into file ".../drivers/net/wireless/realtek/Kconfig" insert line:
source "/drivers/net/wireless/realtek/rtl8723bs/Kconfig"
3. into file ".../drivers/net/wireless/realtek/Makefile" insert line:
obj-$(CONFIG_RTL8723BS)        += rtl8723bs/
4. do : make menuconfig -> device drivers-> network device support -> wireless LAN ->  select 8723bs
5. by hand deselect 8723bs in ".../drivers/staging/Makefile" -- just comment out this line by #, driver 8723bs from staging does not work.
6. do make.
