# `urxvt` configuration reload

This plugin allows you to reload `urxvt` configuration at runtime
by sending `SIGHUP` to the `urxvt` process.

## What can be reloaded?

Currently only color, font and geometry settings are reloaded.

## Why?

  * To switch between a high-contrast and low-constrast color
    schemes based on sunlight levels.
  * To switch font sizes when the terminal is moved to
    another screen with a different DPI.
  * ... and much more!

## Usage

To reload the current terminal (will *only* work from the prompt):

    kill -s HUP $(ps -p $$ -o ppid=)

To reload all terminals

    killall -SIGHUP urxvt

## Dependencies

  * urxvt (obviously)
  * Perl ≥ 5.20 (could be easily fixed to work with more ancient
    versions if needed)
  * AnyEvent
  * Linux::FD
  * common::sense

You can install the needed packages with CPAN:

    sudo cpan AnyEvent Linux::FD common::sense

## Installation

Copy the files into `~/.urxvt/ext/` (local) or `/usr/lib/urxvt/perl`
(system-wide). Alternatively, add the folder path to your `.Xresources`:

    URxvt.perl-lib: /your/folder/

You must add `config-reload` to the `URxvt.perl-ext-common` resource in
`Xresources`:

    URxvt.perl-ext-common: default,clipboard,...,config-reload

**Do not** add the `config-print` extension there!
