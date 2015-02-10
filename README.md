SlimLP
================

Local Manifest to build SlimLP for the Huawei Y300 and G510

Build Instructions
-----------------------------------------------------------------------------
1. Install build software for ubuntu:
		sudo apt-get install bison build-essential curl flex g++-multilib gcc-multilib git-core gnupg gperf lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev libesd0-dev libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev gperf openjdk-7-jdk openjdk-7-jre gcc curl repo python-markdown

	// По мере установки, дополню пакеты...

2. Initialize repo using the SlimLP manifest (CAF branch)
    
		repo init -u git://github.com/SlimRoms/platform_manifest.git -b lp5.0-caf

3. Add my local manifest

		mkdir .repo/local_manifests
		Copy slimlp_huawei.xml to .repo/local_manifests

4. Then sync up the repositories

		repo sync

5. Initialize the build environment

		source build/envsetup.sh
    
6. Build the ROM

		For Y300:
			brunch u8833
		
		For G510:
			brunch u8951

NOTE:
   
   The JNI Generator [patch] included in android_device_huawei_msm7x27a-common is required for building the rom in my Arch Linux environment.
   For Ububtu based distros, this patch should not be needed to build the ROM so can be deleted.

[patch]:https://github.com/SlimLP-Y300/android_device_huawei_msm7x27a-common/blob/lp5.0/patches/external_chromium_org/0001-Fix-JNI-Generator.patch
