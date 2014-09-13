This is a Kicad schematic & PCB footprint library created by
Freetronics.

[Kicad](http://www.kicad-pcb.org) is an open source
[EDA](http://en.wikipedia.org/wiki/Electronic_design_automation)
software package.

Some of the components here may be automatically converted from
pre-existing EAGLE libraries, and may need some manual cleanup before
they're ready for use.

If using the .pretty footprints, this S-expression can be copied to your library table for use with the Github Plugin:

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