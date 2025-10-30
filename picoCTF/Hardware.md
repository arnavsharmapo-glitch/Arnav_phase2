# Challenge 1 : iq test

let your input x = 30478191278.

wrap your answer with nite{ } for the flag.

As an example, entering x = 34359738368 gives (y0, ..., y11), so the flag would be nite{010000000011}.

## Solution : 
- Opened the files i got in the challenge
- One was the description of the challenge which had our input as 30478191278
- Seeing the total number of logic gates on the other file and considering that they only take 0 or 1 as an inout, figured out that we would have to convert the input to a 36 bit binary input
- Got that number as 000001101100011000101001010101011110
- Now, I solved the logic gates and got the flag
![iq test Flag](../pics/iqtest%20(1).png?raw=true)

## Flag : 
```sh
nite{101100100101}
```

## Concepts Learnt :

- Learnt more about logic gates and how to solve them

## Notes : 

No alternate tangents

### Reference : 

None

# Challenge 2 : i like logic

i like logic and i like files, apparently, they have something in common, what should my next step be.

## Solution : 
- I got two files for the challenge, one was a .sal file and the other was the desciption foe the challenge
- Opened the .sal file in Logi2 as i figured out that it was a Sal logic analyser file
- I found a lot of 1's and 0's in the 3rd channel
- Exported that raw data into a file and got a .csv file with all the cluttered data and a comma delimiter
- Went to an comma delimiter to delimit that file and get the text in a readable format
- Opened the file in Excel and saw that there were values attatched to the time stamps
- Searched for a flag in there using the search function and got it

## Flag : 
```sh
FCSC{b1dee4eeadf6c4e60aeb142b0b486344e64b12b40d1046de95c89ba5e23a9925}
```

## Concepts Learnt :

- Learnt about .sal files and how to open them
- Learnt how CTF's often use delimited data to hide information about flags and such 

## Notes : 

Accidentally used find and replace option to remove all numbers from the data resulting in getting the wring flag the first time

### Reference : 
```sh
- https://delim.co/#
```


# Challenge 3 : Bare Metal Alchemist

my friend recommended me this anime but i think i've heard a wrong name.

## Solution : 

-

## Flag : 
```sh

```

## Concepts Learnt :


## Notes : 


### Reference : 
