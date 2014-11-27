This is a KiCad schematic & PCB footprint library created by
Freetronics.

[KiCad](http://www.kicad-pcb.org) is an open source
[EDA](http://en.wikipedia.org/wiki/Electronic_design_automation)
software package.

# Caveats

**Never trust a footprint to be correct**. We recommend printing out your board design on paper at 1:1 scale, and then placing components on top of the paper to check they fit. Do not trust any of the components here will match your parts, until you have seen it with your own eyes! The same goes for anyone else's footprints.

Some of the components here may be automatically converted from
pre-existing EAGLE libraries, and may need some manual cleanup before
they're ready for use.

# Usage

## The Easy Way

### Schematic symbols (easy way)

### Footprints (easy way)

If using the .pretty footprints, this S-expression can be copied to your library table for use with the# Github Plugin:

```lisp
(fp_lib_table
  (lib
    (name freetronics_kicad_pcb_lib)
    (type Github)
    (uri https://github.com/freetronics/kicad_library/freetronics_kicad_pcb_lib.pretty)
    (options "")
    (descr "Testing of GITHUB_PLUGIN for KiCad with the freetonics library.")
  )
)
```

## The Powerful Way

### Schematic symbols (powerful way)

### Footprints (powerful way)


# License


# Conventions

## Diodes

Diodes have pins numbered "A" for Anode and "K" for Cathode instead of 1 & 2. This convention is used in any schematic symbols whose names start with *DIODE* or *LED* and in any footprints with DIODE or LED in the name.

## FETs (Field Effect Transistors)

FETs have pins numbered "G","D","S" for Gate, Drain & Source. Footprints for FETs start with the name FET to indicate they also used this convention.

## 

