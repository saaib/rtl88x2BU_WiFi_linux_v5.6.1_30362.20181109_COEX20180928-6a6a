
# Driver for rtl88x2bu WiFi USB adaptors.

Updated driver for rtl88x2bu based on rtl88x2BU_WiFi_linux_v5.6.1_30362.20181109_COEX20180928-6a6a acquired in companion CDROM of CUDY AC1200 USB adaptor.

```bash
Linux version 5.0.0-27-generic #28~18.04.1-Ubuntu SMP Thu Aug 22 03:00:32 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
```

# DKMS installation.

```bash
git clone https://github.com/usaaib/rtl88x2BU_WiFi_linux_v5.6.1_30362.20181109_COEX20180928-6a6a.git
cd rtl88x2BU_WiFi_linux_v5.6.1_30362.20181109_COEX20180928-6a6a
VER=$(sed -n 's/\PACKAGE_VERSION="\(.*\)"/\1/p' dkms.conf)
sudo rsync -rvhP ./ /usr/src/rtl88x2bu-${VER}
sudo dkms add -m rtl88x2bu -v ${VER}
sudo dkms build -m rtl88x2bu -v ${VER}
sudo dkms install -m rtl88x2bu -v ${VER}
sudo modprobe 88x2bu
```
