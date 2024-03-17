# TXT unix parsing Quick Reference

By Andre Lousa Marques

## Table of contents

TBD

## Search and replace text

Perl can also be used to seach and replace text in files. E.g.: `perl -pi.old -e 's{\t+}{ }g' file.txt`

## Find control characters except newline (0xA) and carriage return (0xD)

`grep  -r '[[:cntrl:]]' --include=*.c --include=*.h ${SOURCES_DIR} | grep -vP "\xA" | grep -vP "\xD" `

## Replace tabs

`sed -i $'s/\t/  /' file.txt` (using bash string syntax https://www.gnu.org/software/bash/manual/bash.html#ANSI_002dC-Quoting)

## Convert lines to columns

`awk -v RS=';' '{print $1}'`

## SED Useful options

`-i.bak` instead of `-i` to create a backup (with `.bak` extension) of the original file before the in-place changes to the file

## TODO

Something to take a list of ids and replace them for another table field
