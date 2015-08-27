How to build Module for Platform
- It is only for modules are needed to using Android build system.
- Please check its own install information under its folder for other module.

[Step to build]
1. Get android open source.
    : version info - Android 4.4.4
    ( Download site : http://source.android.com )

2. Copy module that you want to build - to original android open source
   If same module exist in android open source, you should replace it. (no overwrite)
   
  # It is possible to build all modules at once.
  
3. You should add module name to 'PRODUCT_PACKAGES' in 'build\target\product\core.mk' as following case.
    case 1) e2fsprog : should add 'e2fsck','resize2fs' to PRODUCT_PACKAGES
    case 2) brctl : should add 'brctl' to PRODUCT_PACKAGES
    case 3) ebtables : should add 'ebtables','ethertypes' to PRODUCT_PACKAGES
	case 4) libexifa : should add 'libexifa' to PRODUCT_PACKAGES
	case 5) libexif : should add 'libexif' to PRODUCT_PACKAGES
	case 6) libjpega : should add 'libjpega' to PRODUCT_PACKAGES
	case 7) KeyUtils : should add 'libkeyutils' to PRODUCT_PACKAGES

	ex.) [build\target\product\core.mk] - add all module name for case 1 ~ 7 at once 
		# e2fsprog
		PRODUCT_PACKAGES += \
    		e2fsck \
    		resize2fs
    	
		# brctl
		PRODUCT_PACKAGES += \
    		brctl 
    	
		# ebtables
		PRODUCT_PACKAGES += \
    		ebtables \
    		ethertypes
    	
		# libexifa
		PRODUCT_PACKAGES += \
    		libexifa
	    
		# libexif
		PRODUCT_PACKAGES += \
    		libexif
    	
		# libjpega
		PRODUCT_PACKAGES += \
    		libjpega
    	
		# KeyUtils
		PRODUCT_PACKAGES += \
    		libkeyutils

4. excute build command
   ./build.sh user
