# GXP2loader (node-locked)

This is the top 512 KB of the GXP2 ASIC SPI ROM. It performs SOC 
initialization before validating and jumping into U-Boot. 

The secure boot design contains only one copy each of the micro bootblock, 
shim, and other bootloader code. The OpenBMC build then includes two copies 
of this binary in its secure boot build. 

The code requires a "customer key block" to be located in the SPI ROM to 
boot the next stage. The customer key block is a binary containing the 
customer public key, the ASIC ID this is tied to, and is signed by HPE. 

The gxp2-bootblock-t265.bin binary itself is also signed by HPE using test 
key 21. 

-  GXP2loader-t26x-sgn00.bin:  Contains the secure boot block for T26x 
ASICs, and components are signed with key 0 for production ASICs.

-  GXP2loader-t26x-sgn21.bin:  Contains the secure boot block for T26x 
ASICs, and components are signed with key 21 for debug ASICs in the lab.  
Internal use only.

-  GXP2loader-t277-t280-t285-sgn00.bin:  Contains the secure boot block for 
the T277, T280, and T285 ASICs.  Components are signed with iLO 6 key 0 and 
iLO 5 key 6.

-  GXP2loader-t282-t288-sgn00.bin:  Contains the secure boot block for the 
T282 and T288 ASICs.  Components are signed with iLO 6 key 0 and iLO 5 key 
6.

-  trmb-26x.bin:  Micro boot block for Trinity T260, Trinity T261, and 
Trinity T265.

-  trmb-T277-T280-T285.bin:  Micro boot block for Trinity T280, and Trinity 
T285 (T277 was never built). 

-  trmb-T282-T288.bin:  Micro boot block for Trinity T282, and Trinity 
T288.
