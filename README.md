# pxed-appimage

Appimage wrapper around dnsmasq DHCP/TFTP sets related to network image bootup. It act on
DHCP VENDORCLASS option and later on appropriate file. Currenly it is adjusted to my tagset,
but it can easly be changed within pxed.yml

In nutshell, we are just controling how dnsmasq is acting on frames, simple as that

# Override DHCP/TFTP script by using
* PXED_DHCP_SCRIPT="/path/to/my/script" pxed -i usb0

# Use this 
* If you want to get rid of ISC-DHCP & TFTP-HPA
* If you think that above are overkill or too complex 
* if you think that above are needed only on ocasions
* If you want to have one simple executable for network boot
* If you dont want to clutter you shiny OS

## Installation
> 1. clone this repo
> 2. wget -c https://github.com/$(wget -q https://github.com/AppImage/pkg2appimage/releases -O - | grep "pkg2appimage-.*-x86_64.AppImage" | head -n 1 | cut -d '"' -f 2)
> 3. pkg2appimage pxed.yml
> 4. mv out/*.Appimage /usr/bin/pxed
