## How To Compile TWRP For pd1613 ##
------------------

Sync Omni Repo

First you need to download and sync the omni source
	
		repo init -u git://github.com/omnirom/android.git -b android-7.1
		repo sync
	

## Clone pd1613 twrp repo into your working folder ##
---------------

From a terminal prompt inside your working folder

	git clone https://github.com/Theitfixer85/android_device_vivo_pd1613 -b twrp device/vivo/pd1613
	

## Clone other required repos ##
---------------
	git clone https://github.com/Wzedlare/android_vendor_vivo_pd1613 -b cm-14.1 vendor/vivo/pd1613
	git clone https://github.com/CyanogenMod/android_device_qcom_common -b cm-14.1 deivce/qcom/common
	
	
## Start the build ##
---------------
Type the following in a terminal prompt inside from inside the root of your working folder

	source build/envsetup.sh
	lunch
	select omni_pd1613-userdebug
	make recoveryimage
	
	
## Flashing the recovery ##
---------------
The recovery will be outputted to the following folder

	out/target/product/pd1613/recovery.img
	
Assuming you have fastboot all setup put your phone into bootloader mode and type the following in a terminal prompt within the folder containing the recovery file - or you can drag and drop the file into the terminal window to auto complete the path
	
	fastboot flash recovery recovery.img
	
