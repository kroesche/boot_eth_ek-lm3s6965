boot_eth
========
This is the ethernet boot loader (boot_eth) for Stellaris LM3S
microcontrollers.  This boot loader allows firmware update over
ethernet using the **eflash** host utility (and also some other
utilities from TI).

License
-------
These files are subject to the original TI license from the StellarisWare
distribution.  I have made some minor modifications, but do not change the
license.  I make no additional restrictions or claims on my modifications.
You are free to use and modifiy further my modified version, but you are
still subject to the original TI license.

Summary
-------

This boot loader source code was taken from the StellarisWare
distribution for LM3S, revision 10636.  This is the ethernet
boot loader for the '6965 board (boards/ek-lm3s6965/boot_eth).

I have modified this boot loader to work with my custom version of
**eflash**
(see [stellaris_eflash](https://github.com/kroesche/stellaris_eflash/) repo).
The reason I have a custom version is so that I can use it on my Mac.  See
the notes in the **eflash** repo for more information.

I made the following modifications:

* Changed Makefile to point ROOT at the location of StellarisWare
* Changed bl_config to allow forced update via button press
* Changed uip.c and bl_enet.c to use the non-privileged ports, the same as
  [eflash](https://github.com/kroesche/stellaris_eflash/)

The original commit to this repo is the unmodified TI version of the source
files.  If you want to see the changes I made, diff against the first
commit.

Note
----
When I build this using arm-none-eabi-gcc 4.7.4 I get a lot of type-punned
pointer warnings in bl_enet.c.  I have not bothered to fix this in the
original TI source.

