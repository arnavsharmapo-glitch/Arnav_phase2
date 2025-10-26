# Challenge 1 : GDB baby step 1

Can you figure out what is in the eax register at the end of the main function? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Disassemble this.

## Solution : 
- Open the instance
- Download the file mentioned in the hyperlink
- Use the proper commands to link your files in the windows system to your linux shell
- Change to the directory which holds your debugger file
- Make the file executable
- Launch a GDB and load your file into it
- Disassemble the given binary file and read the contents to find the flag as mentioned
- Enter the flag in the format as mentioned

```sh
arnav@LAPTOP-RJNRTH9M:/mnt/c$ chmod ugo+x debugger0_a
arnav@LAPTOP-RJNRTH9M:/mnt/c$ objdump -d -Mintel debugger0_a | less

[1]+  Stopped                 objdump -d -Mintel debugger0_a | less
```

![GDB baby step1 Flag](../pics/Screenshot%202025-10-26%20005453.png?raw=true)

## Flag : 
```
picoCTF{549698}
```

## Concepts Learnt :

- I learnt how to link the files and programs in my windows system to my linux shells
- Learnt what a GDB is and how to launch it
- Learnt the code to disassemble a binary file and view it's contents in a proper manner

## Notes : 

- Alternate path 1 : Directly write the code to launch GDB and run it

### Reference : 
```sh
- GDB Debugger : https://www.tutorialspoint.com/gnu_debugger/gdb_quick_guide.htm
- Object Dump : https://www.geeksforgeeks.org/linux-unix/objdump-command-in-linux-with-examples/
```

# Challenge 2 : ARMssembly 1

For what argument does this program print `win` with variables 83, 0 and 3? File: chall_1.S Flag format: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits. ex. 5614267 would be picoCTF{0055aabb})

## Solution : 

- Open the instance
- Open the file provided ( It's in assembly language )
- Check what operations the file is performing on the required numbers ,i.e, 83, 0 and 3
- First, shift 83 left by 0 bits
- Secondly, load this shifted value into w1
- Thirdly, divide this loaded value by 3 as given
- Lastly, convert the answer from decimal to hexadecimal and type the flag in the format provided

![ARMssembly 1 Flag](../pics/Screenshot%202025-10-26%20141136.png?raw=true)

## Flag  : 
```sh
picoCTF{0000001b}
```

## Concepts Learnt : 

- Learnt how to read commands given in assembly language
- Performed bitwise shifts anf division as given
- Converted Decimal to Hexadecimal

## Notes : 

 No alternate tangents

 ## Reference : 
 ```sh
 - Defining an ARM fn : https://stackoverflow.com/questions/55518499/how-to-define-an-arm-assembly-function-that-can-be-used-in-c
 - https://keleshev.com/compiling-to-assembly-from-scratch/07-arm-assembly-programming
```

# Challenge 3 : Vault Door 3

This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java

## Solution : 
- Open the instance
- When you click on the link provided, it opens up a java code
- First of all, it states that the password length should be equal to 32
- Next we see 4 for loops which tell us what to do with the string provided below
- Secondly, it states that the characters from the 0 to 7th index are to remain the same
- The characters from the 8th to 16th index are to be put through the operation to enter the (23-i)th chracter
- The evn characters from 17th to 31st are to be put in the operation to enter the (46-i)th character and the odd characters in the same range are to be entered as is
- The string you get after the opweration is to be entered in the picoCTF flag format

![Vault Door 3 Question](../pics/Screenshot%202025-10-26%20185410.png?raw=true)
![Vault Door 3 Solution](../pics/Screenshot%202025-10-26%20185510.png?raw=true)

## Flag : 
```sh
picoCTF{ju5t_a_s1mpl3_an4gr4m_4_u_1fb380}
```

## Concepts Learnt : 

- Learnt a bit about Java commands and how their loops work

## Notes : 
- Alternate path :You can write a loops exactly the opposite of the given problem loops to directly find out the passcode by reversing the code loops

### Reference : 
None
