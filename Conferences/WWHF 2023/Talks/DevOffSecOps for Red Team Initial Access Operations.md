---
Speaker: Joff Thyer
Company: Black Hills Information Security
---
How to pervert CI/CD for fun and profit

## Malware
- Defense landscape is becoming much more difficult.
- "what happened?!?" - people started doing their jobs, lawl.

### The following are protections in place today we have to figure out how to bypass:
Static Artificial Analysis 
- Direct malware hash match
- unencrypted shellcode
- high entropy of binary artifact (anything above 5 is immediately malicious)

Event Tracing for Windows
- Trace and log event raised by user mode apps and kernel mode drivers
- APIs
- MOF, WPP, Trace Logging

Kernel Mode Callbacks

Windows NTDLL API Hooking
- Replace opcode with JMP to EDR/XDR DLL

Process Tree Analysis
- monitor and track process relationships

Memory page scanning
- copy machine code into memory page

Call Stack Tracing and Analysis
- Check to see if any "call"s were made from unbacked memory segment
- unwind the call stack
- Offensive: we can FAKE the stack so it looks legit
- Defense: Kernel-mode hardware enforce stack protection
** Hardware enforced stack protection is a REAL protection!!! **

Kernel Driver Blocklists
- "byovd" - bring your own vulnerable driver
---
Malware development just got crazy hard!
Therefore, we have to turn "malware production services" into CI/CD pipelines.

- obfuscation
- recompilation
- dynamic encryption
- automated packaging
- binary artifact signing
- integrate 3rd party tools
- etc....

Utilize CI/CD to automate EVERYTHING stupid so that you no-longer need to remember to do stupid shit.

