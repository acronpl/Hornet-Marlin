<p align="center"><img src="buildroot/share/pixmaps/logo/marlin-outrun-nf-500.png" height="250" alt="MarlinFirmware's logo" /></p>

<h1 align="center">Artillery Hornet - Marlin 2.1.2 Firmware</h1>

## Cura

### Size 
220 x 220 x 250

### START-G
```
; Script based on an original created by tjjfvi (https://github.com/tjjfvi)
; An up-to-date version of the tjjfvi's original script can be found
; here:  https://csi.t6.fyi/
; Note - This script will only work in Cura V4.2 and above!
; --- Global Settings
; layer_height = {layer_height}
; smooth_spiralized_contours = {smooth_spiralized_contours}
; magic_mesh_surface_mode = {magic_mesh_surface_mode}
; machine_extruder_count = {machine_extruder_count}
; --- Single Extruder Settings
; speed_z_hop = {speed_z_hop}
; retraction_amount = {retraction_amount}
; retraction_hop = {retraction_hop}
; retraction_hop_enabled = {retraction_hop_enabled}
; retraction_enable = {retraction_enable}
; retraction_speed = {retraction_speed}
; retraction_retract_speed = {retraction_retract_speed}
; retraction_prime_speed = {retraction_prime_speed}
; speed_travel = {speed_travel}

G28 ;Home
M420 S1 ;restore mesh ABL
G92 E0 ; reset extruder

;Prime the extruder
G1 Z1.0 F3000 ; move z up little to prevent scratching of surface
G1 X200.0 Y0.2 Z0.3 F5000.0 ; move to start-line position
G1 X100.0 Y0.2 Z0.3 F1500.0 E10 ; draw 1st line
G1 X100.0 Y0.6 Z0.3 F5000.0 ; move to side a little
G1 X200.0 Y0.6 Z0.3 F1500.0 E20 ; draw 2nd line
G92 E0 ; reset extruder

G1 Z1.0 F3000 ; move z up little to prevent scratching of surface
```

### END-G
```
G91; relative positioning
G1 Z1.0 F3000 ; move z up little to prevent scratching of print
G90; absolute positioning
G1 X0 Y200 F1000 ; prepare for part removal
M104 S0; turn off extruder
M140 S0 ; turn off bed
G1 X0 Y300 F1000 ; prepare for part removal
M84 ; disable motors
M106 S0 ; turn off fan
```

Additional documentation can be found at the [Marlin Home Page](https://marlinfw.org/).
