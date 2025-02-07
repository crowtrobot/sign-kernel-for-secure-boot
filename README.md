# sign-kernel-for-secure-boot
Script to make unified kernel images, and sign them for secure boot.  

Have you ever wanted to use Secure Boot but have it actually be secure?  By default "Secure Boot" will boot anything Microsoft has decided your computer should be willing to boot.  That's fine if you trust Microsoft to always do that right, but since they signed Windows, I don't know if I can trust what they consider "secure".  ☺

This script will use ukify.py from the systemd project to bundle the kernel, initrd, command line, and optionally some other stuff into a signle file.  It will then (optionally) sign that file with your Secure Boot certificate to bless that kernel to be booted on your machine.  Then it will copy the file into the EFI filesystem so it can be booted by the systemd-boot bootloader.

Specific steps on using this can be found here: 
https://docs.placeboring.com/protecting-my-laptop-from-offline-attacks/make-secure-boot-yours

For this to work, you need to be using secure boot with your own signing certificate.  I've tested that it works when using systemd-boot as the bootloader, but it probably works just as well with other bootloaders (be sure to set CHECK_AND_SIGN_SYSTEMDBOOT to no if you aren't using systemd-boot).


