# MPMU2 Configuration

## Machine Settings for Cura 4.2.1

The Monoprice Maker Ultimate 2 comes with a custom Cura 3.3 installation.  I took the machine settings from the bundled Cura and copied them over to Cura 4.2.1 as a Custom FFF Printer.  I had to make a few modifications to the default Start G-code, because it comes shipped with some hardcoded values.


```
;(**** start.gcode for Ultimate2  (150S)****)
M104 S150
G28 ; Home extruder
G92 X200 Y150 Z165
G29
G1 Z15 F100
M107 ; Turn off fan
G90 ; Absolute positioning
M82 ; Extruder in absolute mode
M109 S{material_print_temperature_layer_0} ;Initial layer temp
G92 E0 ; Reset extruder position
G1 X140 Y7 Z{layer_height_0} F4000
G1 X40 Y7 Z{layer_height_0} E23 F1000
G92 E0
```
