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

## PCB Labelling (References and Values)

Freetronics does not print designator labels or values on silkscreens, we produce a separate image showing what components are located where. Therefore our footprints are not set up for printing labels on silkscreen. However each footprint can be easily modified for this use.

*Reference* text (usually the name of the footprint in the PCB editor, that become designators like C22 on the board) should be visible on the *Eco1.User* layer. The reference may overlap pads or other features if necessary. Text thickness must be at least 0.1mm, recommended text size 0.6mm x 0.6mm or larger.

The exception is footprints where a name is likely to be printed on the board for the user to see (for example solder jumpers like `SJ2`). In these instances the Reference text goes on the *Front.Silks* layer.

*Value* text (usually the placeholder `val**` in the PCB editor, that becomes the component value on the board) should be Invisible on the *Eco1.User* layer. The value should be placed in such a way that it could be switched to the SilkScreen layer and made visible and legible, without needing rearrangement. Text thickness should be at least 0.1mm, minimum text size 0.6mm x 0.6mm.

*Value* text may be left visible in cases where the footprint area is very large, and the text can fit wholly under the component.

## Outlines

Currently outlines are sometimes on Cmts.User, sometimes on Dwgs.User and sometimes on the silkscreen. Sometimes the outline is the component and sometimes it is the "Courtyard" (area to be left clear around the component for assembly). Eventually this should be cleaned up to use KiCad's new ".Crtyrd" layers for the courtyard, and silkscreen only for outlines which are printed on the board.


## Diodes

Diodes have pins numbered "A" for Anode and "K" for Cathode instead of 1 & 2. This convention is used in any schematic symbols whose names start with *DIODE* or *LED* and in any footprints with DIODE or LED in the name.

## FETs (Field Effect Transistors)

FETs have pins numbered "G","D","S" for Gate, Drain & Source. Footprints for FETs have the suffix _FET to indicate they use this convention. In some cases there may be a standard numbered footprint and a FET version.

## BJT Transistors

BJT transistors (NPN/PNP) have pins numbered "B","C","E" or Base, Collector, Emitter.

## Package Dimensions

Package names should indicate at least one key body dimension as well as pin count, ie
`SO16_4mm` indicates a SOIC 16 pin package with 4mm wide body.

For packages where it is possible for there to be multiple pin pitches, the pin pitch should also be appended to the name - ie `QFN32_0.5mm` indicates a 32 pin QFN with 0.5mm pin pitch.

The suffix _EP indicates an exposed pad in addition to the numbered pins (named `PAD` by convention).




