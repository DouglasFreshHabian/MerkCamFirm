# MerkCamFirm
Firmware that I dumped from a Merkury [MI-CW051] ip camera spi flash chip

The firware in this repo comes from a 1080p Merkury IP Camera. The camera was purchased from 
one of the larget retailers in the world, which starts with a W. The camera was marked down
in price due to the fact that it had already been purchased and returned. After several un-
successful attempts to get the camera working properly and after leaving it on a shelf inside
of a closet for quite a while, I eventually came back across the camera and decided to reverse
engineer it. Using a ch341_spi programmer and the flashrom utility, I was able to read and dump
the contents of the spi flash chip. That firmware blob is here, as is, for anyone else to take
a look at and perform static analysis, emulation, etc. You will find a set of credentials within
that have since been changed. More importantly, there is a backdoor that has been added to the 
image via a dropbear ssh binary as well as access to a root shell. I have yet to be able to verify
if this "backdoor" is something that was added by the vendor before shipment or if perhaps it was
added by a bad actor and then returned back to the very large retailer for someone such as myself 
to then purchase. My belief is that the answer is the latter. As I make more progress in reverse
engineering the firmware and performing static & dynamic analysis, I will add it all to this repo.

The main tools that I have used to get to this point are: 
  flashrom
  strings
  binwalk

Command to dump the firmware:
  sudo flashrom --programmer ch341a_spi --read merkury.bin

Strings command to gather informaton before attempted to unpack and/or decompress the firmware blob
  strings -n 10 merkury.bin

To unpack the firmware, I ran the following binwalk command
  binwalk -eM merkury.bin

Any thoughts and feedback on any of this would be greatly appreciated. Thank you. 

                                                                                Live, Love, Linux
                                                                                Dougas Fresh Habian

  edd
