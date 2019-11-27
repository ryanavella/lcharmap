# `lcharmap`

> A CLI port of the Windows `charmap` utility

### What?

`lcharmap` is a CLI port of the Windows `charmap.exe` utility for Unix.
It displays information for a particular Unicode code point, including
it's hexadecimal/octal and HTML entity representation. 

In the future, it will also display character descriptions and will
allow to search characters based on description. (*TODO*)

### Where?
#### Dependencies
- Windows (*supported, not tested*)
- macOS (*not supported or tested*)
- Linux (*supported and tested*)
- Free|Open|Net|Dragonfly BSD (*not supported, not tested*)

#### Build dependencies
- the Rust compiler toolchain (Stable)
- GNU Make

#### Binaries
In the future, compiled binaries for the following platforms will be
available to download from GitHub Releases:
- Linux (`x86_64 glibc`)
- Linux (`x86_64 musl`)
- Linux (`armv6l glibc`)
- Linux (`armv6l musl`)
- Windows (`x86_64`)
- BSD (`x86_64`)

For now, you must build from source.

#### Building from Source
Clone the project:
```
$ git clone https://github.com/lptstr/lcharmap
```

Build:
```
$ cd lcharmap
$ make release
```

Install (**Linux**)
```
$ make install
```

Install (**Windows**)
```
C:\> copy build\release\lcharmap C:\<install location>
```

*Note: on the installation step, you may need root/admin privileges.*

### How?

Simply run `lcharmap` with a range of characters you want info for:
```
$ lcharmap 65 66
--------------------------------------------------------------------
DEC	HEX	OCT	HTML	CHAR
--------------------------------------------------------------------
65	41	101	&#41;	A
--------------------------------------------------------------------
66	42	102	&#42;	B
--------------------------------------------------------------------
```
You can run it on a single code point (or character!) too:
```
$ lcharmap 67
               decimal  67
           hexadecimal  43
                 octal  103
           HTML entity  &#43;
             character  C

$ lcharmap C
               decimal  67
           hexadecimal  43
                 octal  103
           HTML entity  &#43;
             character  C
```

Run `lcharmap --help`/`man lcharmap` for more information.

### Why?
I miss some Windows utilities.

### License
This lame little utility is licensed under the MIT License. See the `LICENSE.md`
file for more information.