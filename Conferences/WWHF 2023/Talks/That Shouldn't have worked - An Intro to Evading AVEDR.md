---
Speaker: Corey Overstreet
Company: Red Siege
---
What works today won't work tomorrow.
Keep it simple:
- Edit comments
- Edit code that worked yesterday
- Don't focus on making it extremely sexy and complex
- Easy stuff still works....

## Initial Considerations
programming languages:
- C
- C#
- Golang
- Python

Just try different file types before developing a whole new tool.

Executing locally vs downloading may not be detected in the same way. Even just host it yourself - we need to emulate the attackers as much as possible.

#### Zone.Identifier Bypasses
- write a dropper (encode or encrypt the file)
- Containers (zip file, tar, VHD, iso)


## Bypassing Initial Protections
### AMSI - antimalware scanning interface
- loaded into every process through amsi.dll
- used by microsoft defender
- How to bypass this?
	- modify signature strings
	- zero size amsiScanBuffer Patch
	- use Powershell v2 (no amsi integration)

### ETW - event tracing for Windows
- edr products often have this
- all api calls are contained in ntdll.dll
- How to bypass:
	- Obfuscating: mimikatz -> mimidogz
	- patch etw api call hooks

### Syscalls
- NT* and ZW* api calls are proxy to kernel functions
- checkout sektor7 HellsGate and HalosGate

## Getting out of the sandbox
- AV/EDR will execute files in a sandbox to watch for suspicious behavior
- Executed from small virtual machines locally
- Bypasses:
	- Slow down execution (edr cannot slow down performance, therefore, add a few sleeps/long running functions to make the EDR stop executing it. Calculate large prime numbers or do fibonacci sequencing).
	- Make the file to large to fit in the sandbox. (DigDug and Mangle)
- How to detect we're in a sandbox	
	 - Domain status - "check if we're in the target environment". Check domain-joined status. Sandboxes rarely have this information so we can know we're in the sandbox.
	- Host Attribution - monitor resolution, amount of ram, MAC address, number of processor cores, etc.

### Static Detection
- embedded shellcode
- how to bypass:
	- UUIDs
	- embedded in an image file
	- Jargon (0x01 = "cat") - my poetry idea
	- use different encryption keys each time


## General Notes
- do NOT immediately make the C2 callback, this is suspicious. Make the program run a few minutes and do shit and THEN make the callback (and then continue doing shit).
- you can load C# from remote files with webdav
- proxy dll - as designed by MS, proxy function requests to legit dlls, so like inheritance with dlls? (checkout spartan proxy dll generator)