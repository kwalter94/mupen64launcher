# mupen64launcher

This is a quick and dirty frontend for the console version of
the  Nintendo 64 emulator, `mupen64plus`. Running it requires
Perl 5.10+ on Linux/Unix or any OS that can `fork(2)`.

## Installation

Before anything make sure you have a working `Perl 5.10+`
installation and `mupen64plus` by doing the following:

```bash
$ perl -v
```

If you don't have either `Perl` or `mupen64plus` (why are you even
looking at this if you don't have it already) install them by
doing your `apt-get install` or `pkg install` or whatever that
you can do to get Perl on your box.

Next you need to install the required libraries, create the
games directory where you will place your ROMS, and copy the
configuration file to your your home directory:

```bash
$ cpan Config::Simple Tk
$ mkdir -p ~/games/N64/
$ cp mupen64launcher.cfg ~/.mupen64launcher
```

NOTE: The third command above assumes your working directory is
the directory where you have the default configuration file
(comes together with this README and mupen64launcher script).

## Running

EZ as 1-2... Make sure you have your ROMS in `~/games/N64/` then
go to your mupen64launcher directory and do:

```bash
$ perl mupen64launcher
```

NOTE: For some reason you may need to open a ROM twice for it to
successfully start after the very first run. It seems to be an
issue with the Config::Simple library (but it could be me too).
Config parameters are inaccessible for the n-th even access
(ie. for access number 1 - it's there, access number 2 - it
vanishes, access number 3 - it's back, and so on; Quite odd
behaviour for the n-th even access).