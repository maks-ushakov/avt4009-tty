# avt4009-tty
Simple Arduino virtual termial emulator on SPFD5408 320x240 display. 40 columns, 9 rows


Based on [TinTTY](https://github.com/unframework/tintty)

Command set is limited (similar to [VT-05](https://en.wikipedia.org/wiki/VT05)).
C0 in [ANSI X3.64](https://en.wikipedia.org/wiki/ANSI_escape_code)


|^| 	C0 	|Abbr |	Name |	Effect|
|-|-----|-----|------|---------|
|^G| 	0x07| 	BEL| 	Bell| 	Makes an audible noise.|
|^H |	0x08| 	BS |	Backspace |	Moves the cursor left (but may "backwards wrap" if cursor is at start of line).|
|^I| 	0x09| 	HT 	|Tab 	|Moves the cursor right to next multiple of 8.|
|^J| 	0x0A| 	LF |	Line Feed |	Moves to next line, scrolls the display up if at bottom of the screen. Usually does not move horizontally, though programs should not rely on this.|
|^L |	0x0C 	|FF |	Form Feed |	Move a printer to top of next page. Usually does not move horizontally, though programs should not rely on this. Effect on video terminals varies.|
|^M| 	0x0D 	|CR |	Carriage Return |	Moves the cursor to column zero.|
|^[| 	0x1B 	|ESC 	|Escape |	Starts all the escape sequences |
