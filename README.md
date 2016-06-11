# `urxvt` configuration reload

This plugin allows you to reload `urxvt` configuration at runtime
by sending `SIGUSR1` to the `urxvt` process.

## What can be reloaded?

Currently only color settings are reloaded, support for changing
font is planned.

## Why?

  * To switch between a high-contrast and low-constrast color
    schemes based on sunlight levels.
  * To switch font sizes when the terminal is moved to
    another screen with a different DPI.
  * ... and much more!

Example usage scripts might be added later.

## Installation

See https://github.com/muennich/urxvt-perls#installation
