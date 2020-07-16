# memmap
Tool/GUI for viewing and working with memory maps for iBoot

Run with no arguments to trigger the interactive CLI menu

```
memmap.py -h -x --soc=[soc] --model=[model] --target=[target] --value [variable] [variable2]...
-----
Ommiting soc/model or target will launch an interactive GUI where you can select them :)
-----
-h - Print this menu and exit
-x - Print nothing but the addresses, use for piping --value output elsewhere
-s - Specify a SOC (e.g. t8002)
-m - Specify model (e.g. Watch2,3) instead of an SOC
-t - Specify the targeted portion of iBoot (0=SecureRom, 1=LLB iBSS DFU, 2=iBoot iBEC)
-v - Display only the variables after this argument
```

## Examples

`./memmap.py -s t8002 -t 0 -x -v BOOT_TRAMPOLINE_BASE`

Print out the value of BOOT_TRAMPOLINE_BASE for the SecureRom build for the t8002 SOC

`./memmap.py -v HEAP_BASE`

Opens the GUI to allow you to select SOC and target, and then prints only the HEAP_BASE

`./memmap.py -s Watch2,6 -t 0`

Print out the entire memory map for the Watch2,6 SOC's SecureRom.
