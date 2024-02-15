# sign-kernel-for-secure-boot
Script to make unified kernel images, and sign them for secure boot.  

Have you ever wanted to use Secure Boot but have it actually be secure?  By default "Secure Boot" will boot anything Microsoft has decided your computer should be willing to boot.  That's fine if you trust Microsoft to always do that right, but since they signed Windows, I don't know if I can trust what they consider "secure".  ☺

This script will use ukify.py from the systemd project to bundle the kernel, initrd, command line, and optionally some other stuff into a signle file.  It will then (optionally) sign that file with your Secure Boot certificate to bless that kernel to be booted on your machine.  Then it will copy the file into the EFI filesystem so it can be booted by the systemd-boot bootloader.  

When I've finished writting up the entire guide on making your own computer's secure boot work for you, I will link it here.  This script is most useful when used in connection with all of that process.  
