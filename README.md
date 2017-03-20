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

Example usage scripts might be added later.

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

Copy the files into `~/.urxvt/ext/`. Add `config-reload` to the
`URxvt.perl-ext-common` option in `Xresources`. E.g.:

    URxvt.perl-ext-common: default,clipboard,...,config-reload

**Do not** add the `config-print` extension there!

See https://github.com/muennich/urxvt-perls#installation for alternative
installation methods (system-wide etc.).
