# 📸 MerkCamFirm

<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=300&section=header&text=Reverse%20Engineer&desc=IP%20Camera&animation=blinkingrender&fontSize=80" />

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=18ACF7&width=435&lines=Extract+IP+Camera+Firmware;For+Reverse+Engineering;" alt="Typing SVG" /></a>
<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=F71818&width=435&lines=Extract+IP+Camera+Firmware...;For+Reverse+Engineering...;Reverse+Engineering...;IP+Camera+Firmware...;Runtime+Analysis+%26+Exploitation..." alt="Typing SVG" /></a>

## Firmware 💩 Dump of Merkury [MI-CW051] IP Camera (SPI Flash) 🔦

Welcome to [MerkCamFirm](https://github.com/DouglasFreshHabian/MerkCamFirm) – a repository that contains the firmware dumped from the Merkury MI-CW051 1080p IP camera. This project is for anyone interested in exploring, reverse-engineering, or performing security research on the firmware of IoT devices.

The firmware here was extracted using a CH341A SPI programmer and the `flashrom` utility. The resulting firmware image, merkury.bin, is shared in its raw form, enabling anyone to dive into static analysis, emulation, or any other form of research.

## Why This Project? 🗯

The goal of this project is to offer a transparent look into the firmware of a widely used consumer device. As part of my ongoing reverse engineering efforts, I will continue to add insights, static and dynamic analysis results, and modifications to this repository.

Whether you’re a Linux enthusiast, a security researcher, a reverse engineer, or a hacker, this project aims to provide useful resources to help uncover how the firmware operates and potentially identify vulnerabilities, security flaws, or other points of interest.

## Tools: 🛠

### Software: 💾
  1. flashrom:  To interface with the SPI chip.
  2. strings:   For gathering information from the binary.
  3. binwalk:   For unpacking and extracting files from the firmware.

### Hardware: 💻
  1. ch341a_spi bios/eeprom spi flash chip programmer
  2. Computer running Linux (kali Linux, Ubuntu)

## Methodology: 🌍🔎

Probe for the flash chip:
```bash
   flashrom --programmer ch341a_spi
```
Read and dump the firmware:
```bash
    flashrom --programmer ch341a_spi --chip [Chip Name] --read merkury.bin
```
## Basic Analysis of the Firmware: 💻🕵️  
To gather basic strings and identify potential embedded information in the firmware before performing further analysis:
Commands:
```bash
   file merkury.bin                # Determine the file type

   binwalk merkury.bin             # Ran with no options, binwalk will scan the image and print the results to the screen

   strings -n 10 merkury.bin       # Strings will print any sequences of "human-readable" characters, that are atleast 10 characters long (-n 10)

   hexdump -C | head               # Looking for signatures in the header
```
## Unpacking the Firmware: 🔐
To unpack the firmware and extract embedded files or hidden elements, I used binwalk:
```bash
   binwalk merkury.bin             # Ran with no options, binwalk will scan the image and print the results to the screen

   binwalk -E merkury.bin          # Calculates file entropy which tells us whether the firmware is encrypted or not

   binwalk -eM merkury.bin         # Extract known file types (-e), and recursively scan extracted files (-M)
```  





















["Extract IP Camera Firmware For Reverse Engineering"](https://youtu.be/P7yIM5AozEg?feature=shared)


["Reverse Engineering IP Camera Firmware - Full Video"](https://youtu.be/jVe67nDcmy8?feature=shared)



  edd![Screenshot from 2024-11-06 22-26-26](https://github.com/user-attachments/assets/7d6c8884-61ca-4a92-818d-3141868cd6ba)

