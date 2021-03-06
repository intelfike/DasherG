# DasherG
DasherG is a new free terminal emulator for Data General DASHER series character-based terminals.  It is written in [Go](https://golang.org/) using the [Go-Gtk](https://github.com/mattn/go-gtk) toolkit and should run on all common platforms supported by Go.

![screenshot](screenshots/alpha-selftest.png "Alpha Screenshot")

## Key Features

* Serial interface support at 300, 1200, 2400, 4800, 9600 & 19200 baud, 7 or 8 data bits (defaults to 9600, 8, n, 1)
* Network Interface (Telnet) support
* Dasher D200, D210 ~~& D211~~ Emulation
* 15 (plus Ctrl & Shift) Dasher Function keys, Erase Page, Erase EOL, Hold, Local Print and ~~Cmd-Break~~ keys
* Reverse video, blinking, dim and underlined characters
* Various terminal widths, heights and zoom-levels available
* Pixel-for-pixel copy of D410 character set
* Session logging to file
* Loadable function key templates (BROWSE, SED and SMI provided as examples)
* 2000-line terminal history
* May specify ```-host=host:port``` on command line
* Support for mini-Expect scripts to automate some tasks [see Wiki](https://github.com/SMerrony/DasherG/wiki/DasherG-Mini-Expect-Scripts).

## Download
DasherG is [hosted on GitHub](https://github.com/SMerrony/DasherG).

## Build from Source
### Prerequisites
To build from the source you will need the GTK-Development packages installed on your system.  You will also need to install the following Go packages...

```go get github.com/mattn/go-gtk/gtk``` 

and 

```go install github.com/jacobsa/go-serial/serial```

### Build
```go build```

or, if you prefer

```go install```

## Running DasherG
From the build or install directory simply type

```./dasherg```

Optionally, you may add the ```-host=host:port``` argument to connect to a running host via telnet. Eg. 

```./dasherg -host=localhost:23```

### Function Keys
You may have to use the keys simulated on the toolbar in DasherG as your OS might interfere with the physical function keys on your keyboard.  The Shift and Control keys can be used in conjunction with the simulated F-keys just like a real Dasher.

~~The "Brk" key sends a Command-Break signal to the host when connected via the serial interface.~~

"Hold" and "Local Print" work as you would expect, although the print actually goes to a user-specified image (PNG) file.

### Bell Sound

For the system bell to operate, DasherG must have been started from a terminal which supports the bell.

### Emulation Details
[See here](https://github.com/SMerrony/DasherG/blob/master/implementationChart.md)
