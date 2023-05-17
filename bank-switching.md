The [FAQ](https://worldofspectrum.org/faq/reference/128kreference.htm)


* Banks 0, 1, 3, 4 and 6 fall between 49152 (0xC000) and 65535 (0xFFFF).  
* Bank 2 runs from 32768 (0x8000) to 49151 (0xBFFF) and at (0xC000) and 65535 (0xFFFF).
* Bank 5 shows at 16384 (0x4000) to 32767 (to 0x7FFF).
* Bank 7 is a shadow screen for screen flipping.

```
;Bank Switcher
; written by Ast A. Moore on Spectrum Computing
;runs from 32768-32793

org 32768       ; 24210
memory_to_change:
	defb 0

org 32770       ; 24212
	ld a, (memory_to_change)
	ld b, a
	ld A, (#5B5C)   ; in 5B5C is the current memory page

	and $F8
	or b

	ld ($5B5C), A   ; you have to preserve it, or BASIC goes crazy

	ld BC, $7FFD

	di              ;condom on
	ld (23388),a	;write new value back to sys. var
	out (c),a       ;and to port
	ei              ;condom off
	ret             ;we should be back in BASIC now
```


