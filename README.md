# ZX-Spectrum-Tips

## LOAD/SAVE

* Disable the prompt immediately before the SAVE, by changing the input / output functions for the "K" device.
  
```
  900 POKE 23734,111: REM suppress prompt
  910 POKE 23736,20: REM don't wait for keypress
  920 SAVE "image" SCREEN$
```

* LOAD/SAVE headerless files
  [Headerless BASIC command](https://worldofspectrum.net/item/0026892/)

* Free memory for loader (use after CLEAR xxx)
```
PRINT 65536-USR 7962
```
