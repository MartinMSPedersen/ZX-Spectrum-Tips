# ZX-Spectrum-Tips

Disable the prompt immediately before the SAVE, by changing the input / output functions for the "K" device.
```
900 POKE 23734,111: REM suppress prompt
910 POKE 23736,20: REM don't wait for keypress
920 SAVE "image" SCREEN$
```
