# MerkCamFirm
Firmware that I dumped from a Merkury [MI-CW051] ip camera spi flash chip

The firware in this repo comes from a 1080p Merkury IP Camera. Using a ch341_spi programmer and 
the flashrom utility, I was able to read and dump the contents of the spi flash chip. That firmware 
blob is here, as is, for anyone else to take a look at and perform static analysis, emulation, etc. 
As I make further progress in reverse engineering the firmware and performing static & dynamic analysis, 
I will add my personal results from it all to this repo.

The main tools that I have used to get to this point are: 
  flashrom
  strings
  binwalk

Command to dump the firmware:
  flashrom --programmer ch341a_spi
  flashrom --programmer ch341a_spi  --chip [Name of Chip] --read merkury.bin

Strings command to gather informaton before attempted to unpack and/or decompress the firmware blob
  strings -n 10 merkury.bin

To unpack the firmware, I ran the following binwalk command
  binwalk -eM merkury.bin

######################################################################################################
The 'Merkury' Directory Contains Various Pictures of the camera, board and tools...

The 'hashes.txt' file contains various hashes of the "merkury.bin" binary to verify integrity.

I have also chosen to add the user manual for the camera which I acquired usin the fcc id. 

Any thoughts and feedback on any of this would be greatly appreciated. Thank you. 

                                                                                Live, Love, Linux
                                                                                Douglas Fresh Habian

  edd
