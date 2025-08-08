---
title: .XKEE file format
type: default
---

> <img src="../../img/icons/exclamation.png"> This file format has been marked as deprecated.
>
> *See the <page-link href="/wiki/File_Formats/XK2">.XK2 file format</page-link> for the current standard.*

*“XKEE is the language that keys are written in. It's a plain-text version of the <page-link href="/wiki/File_Formats/KEE">.KEE file format</page-link> with slightly more instructions.”* - Jaegerwald, KEE `legacy/py` branch README<sup>[[1](#/wiki/Special:References)]</sup>. Paraphrased.

## Syntax<sup>[[1](#/wiki/Special:References)]</sup>
Each line has an instruction and an argument, split by a space character.
```
<Instruction> <Argument>
```
If a line starts with a semi-colon, it's ignored as a comment.
```
; Comment
```

Instruction arguments are either a value, variable or argument.

<table>
    <tr>
        <th colspan="2">Instructions</th>
    </tr>
    <tr>
        <td><code>LGD<br></code></td><td>Calculates gradient between <code>hx0</code> and <code>hx1</code> then overlays.</td>
    </tr>
    <tr>
        <td><code>GRD<br></code></td><td>Calculates gradient between <code>hx0</code>, <code>hx1</code>, <code>hx2</code> & <code>hx3</code> then overlays.</td>
    </tr>
    <tr>
        <td><code>ADD<br></code></td><td>Shifts the bytes by <code>hx0</code>.</td>
    </tr>
    <tr>
        <td><code>SUB<br></code></td><td>Shifts the bytes by negative <code>hx0</code>. Compiles to <code>ADD</code></td>
    </tr>
    <tr>
        <td><code>HX[0-9]<br></code></td><td>Sets the respective variable.</td>
    </tr>
</table>

<table>
    <tr>
        <th colspan="2">Arguments</th>
    </tr>
    <tr>
        <td><code>TSP<br></code></td><td>Returns the last byte of the current time.</td>
    </tr>
    <tr>
        <td><code>RND<br></code></td><td>Returns a random byte value.</td>
    </tr>
    <tr>
        <td><code>HX[0-9]<br></code></td><td>Returns the respective variable.</td>
    </tr>
</table>

## References
1. ["Writing your own keys"](https://github.com/Jaegerwald/KEE/tree/legacy/py#writing-your-own-keys). *GitHub.com* [KEE `legacy/py` branch](https://github.com/Jaegerwald/KEE/tree/legacy/py). Retrieved August 8 2025.