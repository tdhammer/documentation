---
title: Installing CentOS on Developerbox
permalink: /documentation/enterprise/developerbox/installation/centos.html
---
# Table of Contents

   * [Downloading install media](#downloading-install-media)
   * [Quirks and workarounds for all deployments](#quirks-and-workarounds-for-all-deployments)
      * [[Hardware] USB/PCIe networking](#hardware-usbpcie-networking)
      * [[Firmware] Set O/S Hardware Description to ACPI](#firmware-set-os-hardware-description-to-acpi)
      * [[Install, First boot] Disable incompatible PCIe features](#install-first-boot-disable-incompatible-pcie-features)
   * [Quirks and workarounds for headless servers](#quirks-and-workarounds-for-headless-servers)
      * [[Hardware] Uninstall the graphics card](#hardware-uninstall-the-graphics-card)
   * [Quirks and workarounds for workstations](#quirks-and-workarounds-for-workstations)
      * [[Hardware] Ensure graphics card is in the x16 slot](#hardware-ensure-graphics-card-is-in-the-x16-slot)
      * [[Install, First boot] Disable the nouveau driver](#install-first-boot-disable-the-nouveau-driver)

<!-- Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc) -->

# Downloading install media

The generic installer images are suitable for use on your Developerbox:
http://mirror.centos.org/altarch/7/isos/aarch64/ . Any of the images are
suitable but the Minimal installer it a good compromise between download
size and functionality (~750MB and it is able to install a Minimal
CentOS system without having to configure networking during the
install).

After downloading an installer image, please carefully study the list of
platform quirks and workarounds below. If you need further information
to complete the install process then there is a Developerbox specific
guide to [Booting an operating system installer](./) which can be read
alongside [the documentation on the CentOS
wiki](https://wiki.centos.org/Documentation).

# Quirks and workarounds for all deployments

## [Hardware] USB/PCIe networking

CentOS 7 is based on the v4.11 kernel, released in April 2017.
This kernel version does not include support for the built-in
network interface. This must be worked around by using an external
network device.

Both PCIe or USB network devices are suitable for this, although it is
important to select a device that is already supported by the CentOS
kernel. If in doubt, please ask on the [Developerbox
forum](https://discuss.96boards.org/c/products/developerbox).

## [Firmware] Set O/S Hardware Description to ACPI

CentOS 7 requires that the Developerbox platform hardware be
described using ACPI. The firmware default is to use device
tree to describe the hardware so this must be changed.

To switch to ACPI mode:

 * Press **Escape** once the `Press ESCAPE for boot options` message
   appears
 * Select **Device Manager** and **SynQuacer Platform Settings**
 * Select **O/S Hardware Description** and choose **ACPI**
 * Press **Escape** and then press **Y** to save and exit
 * Press **Escape** again, to return to the main menu
 * Select **Reset**

## [Install, First boot] Disable incompatible PCIe features

Two features must be disabled to allow PCIe to enumerate and allocate
interrupts correctly. Patches to address the underlying issues are
regarded as bug fixes and will be backported to LTS kernels over time.

If your kernel is affected the workaround is described below

For install **and** first boot:

 * Wait for the grub menu to appear, then press **e** to edit the
   commands before booting
 * Use the editor to add `pcie_aspm=off pci=nomsi` to the kernel command line (this
   is the line commencing with the word `linux`)
 * Check this document for any other *[Install]* or *[First boot]*
   workarounds. Once all kernel arguments are updated, boot the kernel
   by pressing **Ctrl-X**.

To make the change permanent:

 * Wait for CentOS to boot, then login and start a Terminal application
 * Edit `/etc/default/grub` as root, for example: `sudo vi /etc/default/grub`
 * Add `pcie_aspm=off pci=nomsi` to `GRUB_CMDLINE_LINUX`
 * Save the file and close the editor
 * Run `sudo grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg` to
   regenerate the grub config files

# Quirks and workarounds for headless servers

## [Hardware] Uninstall the graphics card

If you wish to use your Developerbox as a headless server it is
recommended that the graphics card be removed entirely. When the
graphics card is removed all console activity (both EDK2 menus and the
Linux console) will automatically switch from using the graphics card to
using the debug UART. The debug UART is connected to the micro-USB
socket behind the I/O shield on the back panel.

The automatic switching of the console means the system maintenance
capabilities via the UART are equivalent to those available via
the graphics card, and the power saved as a result of removing the
graphics card is significant.

# Quirks and workarounds for workstations

## [Hardware] Ensure graphics card is in the x16 slot

CentOS 7 is based on a kernel without sufficient support for
Developerbox to access a PCIe graphics card across a bridge.

Both PCIe x1 slots are connected to a bridge. If you have a graphics
card installed in your Developerbox it must use the x16 slot.

## [Install, First boot] Disable the nouveau driver

CentOS 7 configures the kernel to run with 64k pages (because they
improve system performance), however nouveau driver for the GT-710
graphics card included in the kit will not initialize successfully
on kernels that are configured for 64k pages.

This can be worked around by disabling the nouveau driver. This causes
the operating system to fallback to the EFI framebuffer configured by
the firmware. This reduces the graphics card to a dumb device that scans
out from a fixed frame buffer. All 3D operations will be emulated in
software running the Cortex-A53 processors. Running a lightweight
desktop environment with minimal or no use of 3D acceleration
is strongly recommended. No suitable lightweight desktop is included in
the base operating system but XFCE is available via
[EPEL](https://fedoraproject.org/wiki/EPEL) .

For install **and** first boot:

 * Wait for the grub menu to appear, then press **e** to edit the
   commands before booting
 * Use the editor to add `modprobe.blacklist=nouveau` to the kernel command line (this
   is the line commencing with the word `linux`)
 * Check this document for any other *[Install]* or *[First boot]*
   workarounds. Once all kernel arguments are updated, boot the kernel
   by pressing **Ctrl-X**.

To make the change permanent:

 * Wait for CentOS to boot, then login and start a Terminal application
 * Edit `/etc/default/grub` as root, for example: `sudo vi /etc/default/grub`
 * Add `modprobe.blacklist=nouveau` to `GRUB_CMDLINE_LINUX`
 * Save the file and close the editor
 * Run `sudo grub2-mkconfig -o /boot/efi/EFI/centos/grub.cfg` to
   regenerate the grub config files

