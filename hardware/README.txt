Eagle Zip Release
=============

* Save board and schematic
* Create schematic PDF (<proj name>.pdf)
* Create BOM file (<proj name>.xlsx)
    * In schematic editor, execute "run bom.ulp"
    * Change "List Type" to "Values"
    * Change "Output Format" to "CSV"
    * "Save" as <proj name>.csv
    * Use Excel to convert to <proj name>.xlsx
* Execute "make eagle"

Fab Zip Release
===============

* Complete "Eagle Zip Release" steps
* Run CAM processor to generate Gerber files
* Create XYRS pick-n-place files
    * In layout editor, execute "run mountsmd.ulp"
    * Save as <proj name>.mnt and <proj name>.mnb
* Create photoplots PDF (<proj name>_photoplots.pdf)
* Execute "make fab"
