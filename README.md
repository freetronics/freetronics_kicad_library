This is a KiCad schematic & PCB footprint library created by Freetronics.

[KiCad](http://www.kicad-pcb.org) is an open source
[EDA](http://en.wikipedia.org/wiki/Electronic_design_automation)
software program.

Freetronics uses KiCad for a number of our open source hardware designs (our other designs use the program Eagle). We're sharing the KiCad library we've developed, as a tool for other KiCad users.

# Highlights

Things you may find useful here:

* Common SMD parts, including those we commonly use on our board designs.
* Schematic symbols & footprints for Arduino Shields (all Arduino 1.0/R3 compliant, including Mega and Due).
* Schematic symbols & footprints for Raspberry Pi headers & the HAT footprint.

# License

Except for items noted under "Attribution", the schematic symbols and footprints in this library are provided by Freetronics Pty Ltd under the terms of [Creative Commons Attribution Share-Alike License 4.0 CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/) - as described in the file LICENSE.

**This license does not apply to projects designed using parts from this library**. We don't consider such projects to be a modified form of the library, so we encourage you to **publish your own projects under any license you choose** (open or closed). We only require Attribution & Share-Alike if you distribute a modified version of this KiCad library, as a library.

Of course, if your project uses components from this library and you appreciate it then a shout out and a link back is always appreciated, regardless. :)

# Attribution

We are grateful to the following authors of footprints which are included here:

* nicholaslclews published [Arduino Shield footprints for Kicad on Thingiverse](http://www.thingiverse.com/thing:9630) as [CC-BY](http://creativecommons.org/licenses/by/3.0/). These were modified (R3 additions, etc) to become the ones in this library.

A number of the symbols & footprints in this library were automatically imported from Freetronics' internal Eagle libraries some time ago. We believe everything is accounted for, but please let us know if you see anything in this library that you think is wrongly included or missing attribution.

# Words of Caution

**Never ever trust a footprint to be correct**. We recommend checking pinouts and measurements religiously. Before sending a design for fabrication, print it out on paper at 1:1 scale. Place components on top of the paper to check they fit. Do not trust any of the components here will match your parts, until you have verified it yourself! The same goes for anyone else's footprints, too.

This library is provided without any warranty, as described in the file LICENSE.

# Requirements

These libraries will require a recent version of Kicad. Anything from BZR revision 4500 (mid-2014) or newer should be OK. The older versions of KiCad that are often included with Linux distributions are probably not new enough.

# Usage Instructions

KiCad libraries come in two parts. A schematic symbols library file (`freetronics_schematic.lib`) contains schematic symbols which are used in the schematic editor eeschema. A footprint library directory (`freetronics_footprints.pretty`) contains the PCB layout footprints (`.kicad_mod` files), used in the board layout editor pcbnew.

We will show you two possible ways to use the Freetronics libraries with Kicad. "the easy way" takes less work and doesn't require familiarity with git, but we recommend "the powerful way" for long-term or complex projects where you plan to use git for version control.

## Usage: The Easy Way

### Schematic symbols

* Check out the repository or otherwise download the files `freetronics_schematic.dcm` & `freetronics_schematic.lib` to your computer.

* In the KiCad schematic editor (eeschema), choose Preferences -> Set Active Libraries and add the path to `freetronics_schematic.lib`

The KiCad schematic symbols replace quite a few of the common symbols (R for Resistor, C for Capacitor, INDUCTOR, etc). For this reason we recommend moving `freetronics_schematic` to the top of the list of libraries. Eeschema always uses the first matching name it comes across, starting from the top of the list of libraries. Not doing this may have unexpected results as eeschema mysteriously replaces a Freetronics symbol with one from the built-in libraries.

### Footprints

The file `fp-lib-table` in your project directory allows you to associate a list of library paths or URLs with your project. You can edit this library table inside KiCad (in the PCB editor pcbnew, choose Edit -> Library Tables), but if you're just starting out the easiest way is to copy this snippet into a new file `fp-lib-table` in your project directory, then restart KiCad.

```lisp
(fp_lib_table
  (lib
    (name FT)
    (type Github)
    (uri https://github.com/freetronics/freetronics_kicad_library/freetronics_footprints.pretty)
    (options "")
    (descr "Freetronics Kicad library footprints")
  )
)
```

We recommend using the name FT as shown above, this is the prefix shown in footprint assignments and this way it will match the prefix used in schematic symbol default footprints.

If you'd rather not have the library entry point directly to GitHub, you can download the library to another location and update the URI to a simple path. If doing this, change the `type` from "Github" to "KiCad".

## Usage: The Powerful Way

The "powerful way" is how we manage the KiCad library for Freetronics projects hosted on github. It assumes that you are using git for version control of your project, and that you are reasonably familiar with git. This technique is described on the [Library Management wiki page](https://github.com/freetronics/freetronics_kicad_library/wiki/Library-Management).

The main reason for using the "powerful way" is it allows you to version control the libraries in lock-step with your project, so any given revision of your project is always associated with a matching revision of the library.

# Footprint Conventions

See the [Conventions](https://github.com/freetronics/freetronics_kicad_library/wiki/Conventions) wiki page for an explanation of the conventions used in the Freetronics KiCad library. We recommend reading this before trying using the library, as certain conventions will probably trip you up otherwise.

# Bugs

If you find a bug (and especially if you find a wrong/mislabelled footprint), please [raise a Github Issue](https://github.com/freetronics/freetronics_kicad_library/issues) to let us know. If you can send a [Pull Request with a fix](https://github.com/freetronics/freetronics_kicad_library/pulls), even better!

# Contributing New Footprints

We welcome [Pull Requests](https://github.com/freetronics/freetronics_kicad_library/pulls) with contributions of quality footprints (especially tested ones)! Before adding new footprints, please read over the [Conventions page](https://github.com/freetronics/freetronics_kicad_library/wiki/Conventions) on the wiki and try to fit in with these.

Contributions should either your own work that you're happy to provide under a CC license (as per the bulk of the library), or alternatively under another permissive Attribution-type license.
