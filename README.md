
# uImage_builder

***

### THANKS to
__fun_/naobsd__ and __cheeyee__
for [their thread]( http://forum.xda-developers.com/showthread.php?t=1312927 )

---

## HOWTO

__build-image.sh__ and __build-image_recovery.sh__

Before launching this scripts you must build Android.
Later, copy "__uImage_builder__" folder in your device directory

	$ cp uImage_builder $AOSP/device/$MANUFACTURER/$DEVICE/uImage_builder
	$ cd $AOSP/device/$MANUFACTURER/$DEVICE/uImage_builder
	$ ./build-image.sh $DEVICE
	$ ./build-image_recovery.sh $DEVICE

 example:

	$ cd $AOSP/device/amlogic/tm809/uImage_builder
	$ ./build-image.sh tm809
	$ ./build-image_recovery.sh tm809
will make two new folders in AOSP out directory with new
"**uImage**" "**boot.img**" - "**uImage_recovey**" "**aml_autoscript**"

---

__local_build-image.sh__ and __local_build-image_recovery.sh__

Open "__uImage_builder__";

put your kernel into new folder: "$DEVICE/uImage"

and recovery: "$DEVICE/uImage_recovery"

put your new kernel-initramfs into new folder: "IMAGES/NEWKERNEL/$DEVICE/root"

and recovery-initramfs into new folder: "IMAGES/NEWKERNEL/$DEVICE/recovery"

Then launch scripts:

	$ ./local_build-image.sh $DEVICE
	$ ./local_build-image_recovery.sh $DEVICE

Will make two new folders in "uImage_builder/IMAGES/NEWKERNEL/$DEVICE"
named "NEWBOOT" and "NEWRECOVERY" with new
"**uImage**" "**boot.img**" - "**uImage_recovey**" "**aml_autoscript**"

---

__extract-initramfs.sh__

Open "__uImage_builder__";
put your kernel into new folder: "$DEVICE/uImage"

Then launch script:

	$ ./extract-initramfs.sh $DEVICE

Will make a new folders "uImage_builder/IMAGES/INITRAMFS/$DEVICE/initramfs-old"
with your initramfs files.

This is equivalent to "root" folder in AOSP out directory
and you can use this to make new uImage.

---

__overclock-uImage.sh__

The overclock-uImage.sh is tested only for **tm809**. Please pay attention!

Open "__uImage_builder__";
put your kernel into new folder: "$DEVICE/uImage"

Then launch scripts:

	$ ./overclock-uImage.sh $DEVICE

Will make a new folders "uImage_builder/IMAGES/OVERCLOCKED/$DEVICE" with new
"**uImage**" "**boot.img**" overclocked!

---

## DB DEVICES
[Ainol Novo8 Advanced]( http://www.ainol.com/plugin.php?identifier=ainol&module=product&action=info&productid=38/ "link to official page") - _kernel 2.3.4_ --> `tm809`

[Zenithink C91 3a]( http://www.zenithink.com/Eproducts_C91.php?download ) - _kernel 4.0.3_ --> `ZT280_C91-3a`

