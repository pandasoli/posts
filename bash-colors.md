<div align='center'>

# <samp>ANSI Colors</samp>
</div>

> ANSI colors are used by CLI programs to color anything printed on the terminal.  
> With them it is possible to change the font type and (background)color of a text.

PS: [If you are using **C#** you may not need this.](https://learn.microsoft.com/en-us/dotnet/api/system.consolecolor?view=net-8.0)

<br/>
<div align='right'>

## Getting Started
<small>`\\033\[[\d;]+m`</small>
</div>

To print colored text we need to print a code for a specific color before the text to colorize (they are not printed as visible text).  
We are going to learn it in this article.

At first we need a scape character.  
The most used by programming languages are `\033`, `\e` and `\x1b`.

The base pattern is `\033[m` we put the color sequences before the `m` separated by a `;`.  
We can also repeat sequences if needed but never break them (separate sequences that have to be together).

<br/>
<div align='right'>

## Font Effects
</div>

Some terminals/consoles don't support some font effects.  
Make sure yours does.
<br/>

| Code    | Effect                       | Note                                                                         |
|---------|------------------------------|------------------------------------------------------------------------------|
| 0       | Reset presets                | all attributes off                                                     |
| 1       | Bold                         |
| 2       | Light                        | Not widely supported.                                                  |
| 3       | Italic                       | Not widely supported. Sometimes treated as inverse.                    |
| 4       | Underline                    |
| 5       | Blink                        | less than 150 per minute                                               |
| 6       | Rapid blink                  | MS-DOS ANSI.SYS; 150+ per minute; not widely supported                 |
| 7       | Invert colors                | swap foreground and background colors                                  |
| 8       | Conceal                      | Not widely supported.                                                  |
| 9       | Line-through                 | Characters legible, but marked for deletion.  Not widely supported.    |
| 10      | Primary(default) font        |
| 11–19   | Alternate font               | Select alternate font n-10                                             |
| 20      | Fraktur                      | hardly ever supported                                                  |
| 21      | Bold off or Double Underline | Bold off not widely supported; double underline hardly ever supported. |
| 22      | Bold or light off            | Neither bold nor faint                                                 |
| 23      | Not italic, not Fraktur      |
| 24      | Underline off                | Not singly or doubly underlined                                        |
| 25      | Blink off                    |
| 27      | Inverse off                  |
| 28      | Reveal                       | conceal off                                                            |
| 29      | Line-through off             |
| 51      | Framed                       |
| 52      | Encircled                    |
| 53      | Overlined                    |
| 54      | Not framed or encircled      |
| 55      | Overlined off                |
| 60      | ideogram underline           | hardly ever supported                                                  |
| 61      | ideogram double underline    | hardly ever supported                                                  |
| 62      | ideogram overline            | hardly ever supported                                                  |
| 63      | ideogram double overline     | hardly ever supported                                                  |
| 64      | ideogram stress marking      | hardly ever supported                                                  |
| 65      | ideogram attributes off      | reset the effects of all of 60-64                                      |

<br/>
<div align='right'>

## 2-bit colors
</div>

We use the **30**s for text colors,  
and the **40**s for background colors.

`0` Black  
`1` Red  
`2` Green  
`3` Brown  
`4` Blue  
`5` Purple  
`6` Cyan  
`7` White  
`8` (reserved for higher level colors)  
`9` Default color

It's good to remember that these colors are not static since they can be changed by the user in the terminal settings.

<br/>
<div align='right'>

## 4-bit colors
</div>

> Bright colors

![Table of 4-bit colors for consoles](https://i.stack.imgur.com/9UVnC.png)
<br/>

Now we can use the **90**s for bright text colors,  
and the **100**s for bright background colors.

<br/>
<div align='right'>

## 8-bit colors
</div>

> More possibilities (256)

![Table of 256 possibilities of colors](https://i.stack.imgur.com/KTSQa.png)
<br/>

Now, we can choose a color and use it with the pattern `\e[38;5;<color>m` for text colors,  
and `\e[48;5;<color>m` for background colors.

<br/>
<div align='right'>

## RGB
</div>

> All the colors
<img alt='RGB circle' height='240' align='right' src='https://i.stack.imgur.com/01XJ7.png'/>

To use a RGB color we need the pattern `\e[38;2;<r>;<g>;<b>m` for text colors,  
and `\e[48;2;<r>;<g>;<b>m` for background colors.

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

<br/>
<div align='right'>

## Examples
</div>

> _"Failing and making stupid questions are the best way to learn."_
<br/>

- `\e[1;38;2;124;58;237m`
  - `1` - Bold
  - `38;2; < 124;58;237 >` - RGB purple text color
- `\033[1;4;31m`
  - `1` - Bold
  - `4` - Underline
  - `31` - Red text color
- `\x1b[1;31mSNES Manager \x1b[23mthe best`
  - `1` - Bold
  - `31` - Red text color
  - `23` - Bold off

<br/>
<hr/>
<small>

I already had all this info but [this answer in the StackOverFlow](https://stackoverflow.com/a/33206814/15286947) (recommended) helped me to take it out of my head and taught new stuff.  
Credits also for [Richard](https://stackoverflow.com/users/752843/richard) (the answer's owner).

© 2023 Panda Soli
</small>
