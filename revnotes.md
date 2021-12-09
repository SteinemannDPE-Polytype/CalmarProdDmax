# REVISION NOTES: plc_projects\dp-st-1005-Steinemann4


* Responsible: BRM, FAF, HOA
* Requirement documents:
    * Specification:
    * Implementation:
* Design document ref:

Repository: [GIT repo](http://git.polytype.com/BonoboGit/plc_product_dmax.git)

---
### changes `2.0.0.8` BRM
* FIX: 4p Correction PUC calculation (x inversed), CHG: 4p Correction PLC adapt step size

### changes `2.0.0.7` BRM
* CHG: enable SheetDetect in machine manual mode (not automatic) if the `ManualTeach` mode is active. Needed for camera calibration by hand.

### changes `2.0.0.6` HOA
* CHG: add 4p correction point calculation and update from PCU

### changes `2.0.0.5` BRM
* CHG: add DropSpeed Dead/Add time correction calculation

### changes `2.0.0.4` BRM
* CHG: fix related sub-libraries according main project
* CHG: Apply SpeedComp on X0 instead XS in Attach() of FB_WokerDefGrid_Print

### changes `2.0.0.3` BRM
* CHG: change FB_DropSpeedComp, configurable over persisted Properties.

### changes `2.0.0.2` BRM
* CHG: increase VISU_DMAX_Settings position settings to [um] resolution 6 floating points

### changes `2.0.0.1` BRM
* CHG: use library CompPrint >=2.0.1.12
* CHG: abstract mark id from array index (QV definition)
* FIX: cam point id search
* FIX: crash in FB_MESSAGE (commented, but not resolved)
* FIX: UDINT to DINT conversion error

## `2.0.0` 11.05.2021
Initial version created. 
Contains Camera and DeformationGrid specific code. Currently only from Print-Module. 

---

The revision number consists of three numbers:
`xx.yyy.zzz`

Revnum | Description   | Start Val | Change at
-------|---------------|-----------|-----------
`xx`   | major rev     | 1         | Changes with behavior and interface changes.<br>If you can't exchange the previous version with this one <br>(without ANY source code change in your product) <br>this new version shall be a new major revision number.
`yyy`  | minor rev     | 0         | Changes with code changes and interface extensions.
`zzz`  | bugfix number | 0         | Changes with bugfixes.


> Polytype AG 2021 
> 