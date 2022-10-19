by Mike Sonders @ Red Siege

## Things that get you caught:
---
- Sticking with defaults
	- change comments, variable names, math, etc
- not obfuscating common code execution patterns
- Strings
- Help messages


## Evasion
---
- Multibyte Key + encrypted binaries
- compiler optimization can KILL you! so turn it off!
- Rename entry points, i.e. `VirtualAlloc` -> `SplendidDragon`
- We want EVERYTHING to LOOK like it belongs on the system.

#### Entropy (in information theory):
- Roughly: high entropy == more random == less compressible == easier detection
- Dont randomize too much in your code, just use weird things like "var SplendidDragon" vs "var wecoUse03_32dxclcasdf" or whatever...

How do we lower entropy?
- using written words instead of random crap
- Hell, add a string array with thousands of dictionary words and compile without optimization...

### TOOL: [Jargon](https://github.com/hardwaterhacker/jargon.git)
What if we had a shellcode loader that didnt have any shellcode at all?
Make a wordlist and each word's index location is the "shellcode" integer value equivalent. Then convert your shellcode into integer values, and replace the values with the words... now you can have a "story/poetry/random word list" be your code instead of "raw" shellcode.

# IDEA: What if our shellcode wordlist was the number of characters in the string value?

misc:
- sliver has a go routine link that does a lot of awesome bypasses for us
- checkout sektor7