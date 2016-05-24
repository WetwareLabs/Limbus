## Diptrace schematics and PCB layout files for Limbus Model D

You can open these files directly in Diptrace, but to successfully edit them with correct work-flow requires that libraries are set up correctly, since many components contain references to my custom component library.

First copy the library files (components and patterns) from top level repository directory to your Diptrace Library directory.

Unfortunately the way Diptrace currently handles the references to libraries is that even if you set up these new libraries in Diptrace (via Library / Library Setup), every component in schematic and PCB layout file has a reference to the library file name and path individually. It can be tedious to change them by hand, so use this method:
- export schematic to Diptrace .asc
- with text editor change all "LibPath" references quickly with Find/Replace to correct filename and path
- import schematic again and save
- load PCB file and check that it references the correct schematic (File / Layout Information)
- then do File / Renew layout from Schematic


