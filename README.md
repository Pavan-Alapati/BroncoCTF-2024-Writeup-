# BroncoCTF-2024-Writeup

## Solutions for Categories Easy - Hard (Nice CTF TBH)
Successfully secured a top 20 position :)
# Beginner

## Keyboard Elitist (Beginner)

#### Description
My buddy is bragging about how cool his Framework laptop is and how much faster he can type than me.    When I tried to type a message, it came out as garbage! .
### Encoded
> " A;;apfkgij gj;ukd ar ut ghur war a Qwfpgj efjbyaps yk a Cyifmae uk;lg rchfmf maefr ghur iyye iuef dapbadf. Mj tpufks ur sftukugfij a efjbyaps rkyb, ylg hfpf wugh hur mysliap tpamfwype ia;gy;. Rudh, fughfp waj... hfpf ur ghf tiadO bpykcy{qwfpgj_vr_c0ifm@e} "
The challenge "Keyboard Elitist" involved decrypting a message that appeared as garbage text. Upon decryption, the message revealed that it was encrypted using a keyboard layout shift. By switching to the qwerty layout, the message became decipherable. 
### Decrypted text
> Apparently typing as if this was a Qwerty keyboard on a Colemak input scheme makes this look like garbage. My friend is definitely a keyboard snob, out here with his modular framework laptop. Sigh, either way... here is the flag: `bronco{qwerty_vs_c0lem@k}`.
# Additional Resources
You can find more information about keyboards [here](https://cubedhuang.com/extras/misc/keyboards/).


###  -------------------------------------------------------------------------------------------------------


## Shrekanana Banana   (Beginner)
### Description:
I was given this image of Shrek in a Banana, but I can't help but feel like I am missing something...
[Image](https://github.com/Pavan-Alapati/BroncoCTF-2024-Writeup-/blob/main/ShrekananaBanana.png)
Flag- `brocon{shr3konogr@phy}`
# Additional Resources
Decrypted flag from the image [ decrypted image ](https://aperisolve.com/a3c60e55a2530a19a9e790c33606bee4)
You can find more information about this [here](https://aperisolve.com/)


###  ------------------------------------------------------------------------------------------------------

## Stego-Snore-Us   ( Beginner )

### Description:
I'm not the only one tired after pulling an all-nighter for Hack for Humanity...
### Solution:
Same as the previous, but it's encoded:
Encoded [Image](https://github.com/Pavan-Alapati/BroncoCTF-2024-Writeup-/blob/main/stego-snore-us.png)
### Decoded image with encrypted text in it
[Image](https://aperisolve.com/a5bd460a79d77fad3aeef228925fe795)
## After soo much time i got this is From pesxas to bronco seems like a mono-alphabetic cipher, use the manual decryption mode with this tool, using the description as a guideline.
[tool used to decrypted ](https://www.dcode.fr/monoalphabetic-substitution)
> final solution :- bronco{no_more_all_nighters}

###  ------------------------------------------------------------------------------------------------------

# Forensics
## Medieval Beats 
### Description:  Check out my youtube video
 ( https://youtu.be/rTsABVevwFk )
 ### Solution:
This is a 1 hour video with characters of the flag coming up in random frames throughout. First I downloaded the video at the lowest resolution possible with some generic online tool. Then I extracted one frame each second (~3600 total) and deleted all the black frames which were 284 bytes.
> ffmpeg -i flag.mp4 -vf "fps=1" output_%04d.png
find . -type f -size 284c -exec rm {} +

# Go through the remaining images to get the flag
bronco{1n_17_f0r_7h3_10n6_h4ul}

###  ------------------------------------------------------------------------------------------------------

## Wario Party 

### Description:
Who is the true hero of the Mario Party games you might ask? Look inward and you might find it at the intersection of Mario's color and the number of brothers.
- Note: This flag is wrapped in broncosec{}
### Solution:
Opening the image in aperisolve, we can see some data encoded in one of the bits.
> bronco{b0ws3r_g0t_th4t_dumpy}


###  ------------------------------------------------------------------------------------------------------

## Boom

### Description:
With all these talks of arbitration, things are tense here around the office. I feel like people are going to explode at any moment. I gotta watch where I step before I accidentally bring something up and uncover something I didn't want to.
### Solution:
A file is attached named HarvestBroom.mbf. I added the newlines where there was an obvious pattern (and left in my notes when I made initial observations).
```
7d 19 01 2e 
# Missing 0c
03 01 04 01 05 01 06 01 07 01 08 01 09 01 0a 01 0b 01 0d 01 0e 01 0f 01 10 01 11 01 12 01 13 01 14 01 15 01 16 01 17 01 18 01 19 01 1a 01 1b 01 1c 01 1d 01 1e 01 1f 01 20 01 21 01 22 01 23 01 24 01 25 01 26 01 27 01 28 01 29 01 2a 01 2b 01 2c 01 2d 01 2e 01 2f 01 30 01 31 01 32 01 33 01 34 01 35 01 36 01 37 01 38 01 39 01 3a 01 3b 01 3c 01 3d 01 3e 01 3f 01 
03 02 3f 02 
03 03 3f 03 
03 04 3f 04 
# 1f 20 39 3a 3f
03 05 1f 05 20 05 39 05 3a 05 3f 05 
# 06 1f 2b 2c 2d 2e 2f 3a 3f
03 06 06 06 1f 06 2b 06 2c 06 2d 06 2e 06 2f 06 3a 06 3f 06 
# 06 1e 23 2b 2f 37 3b 3f
03 07 06 07 1e 07 23 07 2b 07 2f 07 37 07 3b 07 3f 07 
# 06 1f 23 2b 2e 2f 31 37 3a 3f 53 57 59 5a 5b
03 08 06 08 1f 08 23 08 2b 08 2e 08 2f 08 31 08 37 08 3a 08 3f 08 53 08 57 08 59 08 5a 08 5b 08 
# missing 09, 0d, 11, 15, 19, 1d, 1f, 20, 21, 22, 26, 2a, 2c, 2e, 30, 33, 35, 36, 38, 39, 3a, 3c, 3d, 3e
03 09 06 09 07 09 08 09 0a 09 0b 09 0c 09 0e 09 0f 09 10 09 12 09 13 09 14 09 16 09 17 09 18 09 1a 09 1b 09 1c 09 1e 09 23 09 24 09 25 09 27 09 28 09 29 09 2b 09 2d 09 2f 09 31 09 32 09 34 09 37 09 3b 09 3f 09 54 09 56 09 59 09 5c 09 
03 0a 06 0a 08 0a 0a 0a 0e 0a 10 0a 12 0a 14 0a 16 0a 1a 0a 1c 0a 1f 0a 23 0a 25 0a 27 0a 29 0a 2b 0a 2c 0a 2f 0a 31 0a 33 0a 35 0a 3a 0a 3f 0a 55 0a 59 0a 5c 0a 
03 0b 06 0b 07 0b 08 0b 0a 0b 0e 0b 0f 0b 10 0b 12 0b 14 0b 16 0b 17 0b 18 0b 1a 0b 1b 0b 1c 0b 1f 0b 20 0b 23 0b 24 0b 25 0b 27 0b 28 0b 29 0b 2b 0b 2c 0b 2d 0b 2e 0b 2f 0b 31 0b 33 0b 35 0b 37 0b 39 0b 3a 0b 3f 0b 54 0b 56 0b 59 0b 5c 0b 
03 0c 3f 0c 53 0c 57 0c 59 0c 5a 0c 5b 0c 
03 0d 3f 0d 
03 0e 04 0e 05 0e 06 0e 07 0e 08 0e 09 0e 0a 0e 0b 0e 0c 0e 0d 0e 0e 0e 0f 0e 10 0e 11 0e 12 0e 13 0e 14 0e 15 0e 16 0e 17 0e 18 0e 19 0e 1a 0e 1b 0e 1c 0e 1d 0e 1e 0e 1f 0e 20 0e 21 0e 22 0e 23 0e 24 0e 25 0e 26 0e 27 0e 28 0e 29 0e 2a
```
#### Boom and Broom, as well as the fact that these seem to be coordinates makes me think of a minesweeper field. If every pair of numbers (ignoring the 4-byte header and the 03 designating a row) is an x/y location, it may be able to print a flag

```

hex_data = "7d 19 01 2e 03 01 04 01 05 01 06 01 07 01 08 01 09 01 0a 01 0b 01 0d 01 0e 01 0f 01 10 01 11 01 12 01 13 01 14 01 15 01 16 01 17 01 18 01 19 01 1a 01 1b 01 1c 01 1d 01 1e 01 1f 01 20 01 21 01 22 01 23 01 24 01 25 01 26 01 27 01 28 01 29 01 2a 01 2b 01 2c 01 2d 01 2e 01 2f 01 30 01 31 01 32 01 33 01 34 01 35 01 36 01 37 01 38 01 39 01 3a 01 3b 01 3c 01 3d 01 3e 01 3f 01 03 02 3f 02 03 03 3f 03 03 04 3f 04 03 05 1f 05 20 05 39 05 3a 05 3f 05 03 06 06 06 1f 06 2b 06 2c 06 2d 06 2e 06 2f 06 3a 06 3f 06 03 07 06 07 1e 07 23 07 2b 07 2f 07 37 07 3b 07 3f 07 03 08 06 08 1f 08 23 08 2b 08 2e 08 2f 08 31 08 37 08 3a 08 3f 08 53 08 57 08 59 08 5a 08 5b 08 03 09 06 09 07 09 08 09 0a 09 0b 09 0c 09 0e 09 0f 09 10 09 12 09 13 09 14 09 16 09 17 09 18 09 1a 09 1b 09 1c 09 1e 09 23 09 24 09 25 09 27 09 28 09 29 09 2b 09 2d 09 2f 09 31 09 32 09 34 09 37 09 3b 09 3f 09 54 09 56 09 59 09 5c 09 03 0a 06 0a 08 0a 0a 0a 0e 0a 10 0a 12 0a 14 0a 16 0a 1a 0a 1c 0a 1f 0a 23 0a 25 0a 27 0a 29 0a 2b 0a 2c 0a 2f 0a 31 0a 33 0a 35 0a 3a 0a 3f 0a 55 0a 59 0a 5c 0a 03 0b 06 0b 07 0b 08 0b 0a 0b 0e 0b 0f 0b 10 0b 12 0b 14 0b 16 0b 17 0b 18 0b 1a 0b 1b 0b 1c 0b 1f 0b 20 0b 23 0b 24 0b 25 0b 27 0b 28 0b 29 0b 2b 0b 2c 0b 2d 0b 2e 0b 2f 0b 31 0b 33 0b 35 0b 37 0b 39 0b 3a 0b 3f 0b 54 0b 56 0b 59 0b 5c 0b 03 0c 3f 0c 53 0c 57 0c 59 0c 5a 0c 5b 0c 03 0d 3f 0d 03 0e 04 0e 05 0e 06 0e 07 0e 08 0e 09 0e 0a 0e 0b 0e 0c 0e 0d 0e 0e 0e 0f 0e 10 0e 11 0e 12 0e 13 0e 14 0e 15 0e 16 0e 17 0e 18 0e 19 0e 1a 0e 1b 0e 1c 0e 1d 0e 1e 0e 1f 0e 20 0e 21 0e 22 0e 23 0e 24 0e 25 0e 26 0e 27 0e 28 0e 29 0e 2a 0e 2b 0e 2c 0e 2d 0e 2e 0e 2f 0e 30 0e 31 0e 32 0e 33 0e 34 0e 35 0e 36 0e 37 0e 38 0e 39 0e 3a 0e 3b 0e 3c 0e 3d 0e 3e 0e 3f 0e 1c 13 1e 13 2e 13 30 13 1b 15 1f 15 2d 15 2e 15 2f 15 30 15 31 15 1c 16 1d 16 1e 16 2d 16 31 16 2e 17 2f 17 30 17"

# Convert the hex data string into a list of bytes
data_bytes = bytes.fromhex(hex_data)

# Define a function to parse the hex data into a structure representing the map
def parse_map(data):
    # Skipping the first 4 bytes (header)
    data = data[4:]

    # Initialize map representation
    map_representation = [["O" for _ in range(0x5c)] for _ in range(0x17)]

    # Iterate over the data to fill in the map
    row = -1
    for i in range(0, len(data), 2):
        if data[i] == 0x03:  # New row marker
            row += 1
        else:
            if row >= 0:  # Ensure we've started processing rows
                col = data[i] - 1  # Adjust for 0-index
                map_representation[row][col] = "X"

    return map_representation

# Parse the map
map_representation = parse_map(data_bytes)

# Function to print the map
def print_map(map_representation):
    for row in map_representation:
        print(" ".join(row))

# Print the map
print_map(map_representation)
```
> Solution bronco{bo0m!}

###  ------------------------------------------------------------------------------------------------------

## Mystery Sound
