# BroncoCTF-2024-Writeup

## Solutions for Categories Easy - Hard (Nice CTF TBH)
Successfully secured a top 20 position :)

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

