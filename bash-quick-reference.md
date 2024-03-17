# Shell Scripting Quick Reference

By Andre Lousa Marques

## Table of contents

TBD

## Tips for running scripts in Windows (Cygwin)

When running scripts (e.g.: bash) in Cygwin, ensure that the scripts are saved with Linux endings.

## Tips for handling numeric values from parsed text

When taking numeric variables from a text file using grep, ensure that it has no hidden characters like  \n or \r

## Sed

To expand a bash variable in sed, use double quotes instead of single quote:

`sed -i "/s/^TimeoutValue.*$/TimeoutValue = ${timeout_value}/"`
