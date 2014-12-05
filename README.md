LTTng-Android
=============

This project aims to facilitate the compilation of LTTng for Android platform. 
Makefiles are provided in order to build dependencies, difference LTTng projects 
and package/install it on your Android device.

Quick start
-----------

In order to compile every LTTng package that have been ported at the moment : 

### NDK [may not work]
1. Download Android [SDK](http://developer.android.com/sdk/index.html) ``make download-sdk`` and [NDK](http://developer.android.com/tools/sdk/ndk/index.html) ``make download-ndk``. If you already have those, skip this step and fill SDK and NDK variables in ``fille_out.mk``. 
2. Fill the file named ``fill_out.mk`` with your own informations
3. Run the following commands

```bash
git clone git://github.com/flatzo/LTTng-Android.git
make            
make package
make push-package
```
 
### AOSP [prefered]
1. Download android source, refer to [AOSP](https://source.android.com/source/initializing.html)
2. Fill the file named ``fill_out.mk`` with required informations. You can leave out kernel and ndk related stuff.
3. Build dependencies in Android tree using ``mm``
 * libext2/uuid
4. Run the following commands

```bash
git clone git://github.com/flatzo/LTTng-Android.git
make            
make package
make push-package
```


Building from AOSP tree
-----------------------

### Build dependencies

* liboprofile/libpopt
* libxml2
  * Add to Android.mk ``LOCAL_CLFAGS += -DLIBXML_SCHEMAS_ENABLED``
