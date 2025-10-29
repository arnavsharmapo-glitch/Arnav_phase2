# Challenge 1 : Trivial File Transfer Protocol

Figure out how they moved the flag.

## Solution : 
- Open the given .tcap file in wireshark for traffic analysing
- There you will find an instruction file, a plan file and 3 images
- Export these files using File -> Export Objects -> tftp
- Decrypt the instruction file using ROT13 to know what needs to be done afterward
```
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
```
- Similarly with the plan file using ROT 13
```
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
```
- This means that the flag is hidden in one of the images
- I checked online and found out that this was called steganography and was used quite commonly in cryptography field
- Researched further and found out the command to find the hidden text, it was steghide
- Used it on all 3 images and found out the flag on the third
- You also have to enter the passcode as mentioned in the plan file which was DUEDILIGENCE
- Paste the flag you got
![tftp analyser](../pics/Screenshot%202025-10-27%20230743.png?raw=true)

## Flag : 
```sh
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

## Concepts Learnt :

- ROT 13 encryption and decryption
- Learnt about steganography and how to use some sites for that online
- Learnt how to analyse network traffic using applications such as WireShark

## Notes : 

Didn't understand what to do at all at first. Then had to look up how to open that kind of file and proceeded with how to export the informatuion from that file onto the windows system. Was able to solve the challenge after that 

### Reference : 
```sh
- https://www.dcode.fr/cipher-identifier
- https://www.dcode.fr/rot-13-cipher
- https://www.edureka.co/blog/steganography-tutorial
```


# Challenge 2 : tunn3l v1s10n

We found this file. Recover the flag.

## Solution : 
- First, downloaded the file, it didn't have any extension
- I then used exiftool command to check the information about the file
```sh
arnav@LAPTOP-RJNRTH9M:/mnt/d/SteamLibrary/picoctf$ exiftool tunn3l_v1s10n
ExifTool Version Number         : 12.76
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2025:10:25 16:56:59+00:00
File Access Date/Time           : 2025:10:29 08:37:25+00:00
File Inode Change Date/Time     : 2025:10:28 17:31:08+00:00
File Permissions                : -rwxrwxrwx
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Unknown (53434)
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Red Mask                        : 0x27171a23
Green Mask                      : 0x20291b1e
Blue Mask                       : 0x1e212a1d
Alpha Mask                      : 0x311a1d26
Color Space                     : Unknown (,5%()
Rendering Intent                : Unknown (826103054)
Image Size                      : 1134x306
Megapixels                      : 0.347
```
- Then I converted the .bmp file to a .jpg file using an image converter
![tunn3l v1s10n ](../pics/Screenshot%202025-10-29%20141628.png?raw=true)
- Unfortunately, we got a text saying notaflag{sorry}
- This must mean that I needed to manipulate the original file and the hints were related to conversion as well
- I found out a hex editor fot the purpose and started changing the height and width of the image
- Altering the width seemed to corrupt the image, so I started increasing the height of the image
- Finally after setting the height of the image to 830 pixels, i was able to find out the flag 
![tunn3l v1s10n flag](../pics/Screenshot%202025-10-29%20141856.png?raw=true)

## Flag : 
```sh
picoCTF{qu1t3_a_v13w_2020}
```

## Concepts Learnt :

- Learnt about hex values and headers
- Leading bits identification using the exiftool command
- Hex editing

## Notes : 

- Zooming in to find a flag
- Using online tools to search for hidden layers
- Trying to find any QR code or scanner in the image which could give us some information

### Reference : 
```sh
- https://en.wikipedia.org/wiki/List_of_filename_extensions_(A%E2%80%93E)
- https://online.reaconverter.com/
```


# Challenge 3 : m00nwalk

Decode this message from the moon.
- Hint 1 : How did pictures from the moon landing get sent back to Earth?
- Hint 2 : What is the CMU mascot?, that might help select a RX option

## Solution : 
- Open instance
- I saw the first hint and checked online about the same
- I found out that they used SSTV(slow scan television) for that
- Also, I found out that there is a SSTV decoder online, which I used to upload the .wav audio file and got the flag 
![m00nwalk flag](../pics/decoded-image.png?raw=true)

## Flag : 
```sh
picoCTF{beep_boop_im_in_space}
```

## Concepts Learnt :

- Learnt about SSTV files and how they were used to get pics from the moon landing

## Notes : 

Tried to put the audio file on a morse code decoder before i read the hints and realised that was completely wrong

### Reference : 
```sh
- https://sstv-decoder.mathieurenaud.fr/
```
