# <samp>Bash Colors</samp>

> **Bash colors** are used by CLI programs to color anything printed on the terminal.  
> With them it is possible to change the type, color and background color of a text.

PS: [If you are using C# you don't need this.](https://learn.microsoft.com/en-us/dotnet/api/system.consolecolor?view=net-8.0)

<br/>

## Using
At first you need a escape character for the key ESC.  
The most used for programming languages are `\033`, `\e` and `\x1b`.

The pattern is this: `\\033\[[\d;]+m`

<br/>

## Font type
- `0` - None
- `1` - Bold
- `2` - Light
- `3` - Italic
- `4` - Underline
- `5` - Blinking
- `7` - Reverse
- `8` - Hidden
- `9` - Line-through
- `21` - Double underline
- `53` - Overline

<br/>

## Text colors
To use colors you need to put a prefix followed by a color code number.

**Background colors** need the prefix `4`.  
**Font colors** need the prefix `3` or `9`.

**Colors' base**
- `0` - Black
- `1` - Red
- `2` - Green
- `3` - Brown
- `4` - Blue
- `5` - Purple
- `6` - Cyan
- `7` - Light gray
- `8` - White

<br/>

## Examples
- `\033[1;43;31m` - Bold font, brown text and red background
- `\033[41;32m` - Red background and green text
- `\033[3m` - Italic font
- `\033[2;31m` - Light font and red text
- `\033[1;3m` - Bold and italic font

<br/>
<br/>

<small>This post was only tested in a **XFCE terminal**, so this codes may not work for other terminals.</small>
