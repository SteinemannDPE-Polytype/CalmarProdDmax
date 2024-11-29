# REVISION NOTES: CalmarProductSteinemann

* Library for Steinemann specific implementations
* Repository: [GIT repo](http://gitlab.polytype.com/calmar/plc/steinemann/library/CalmarProductSteinemann.git)

---

## `3.0.x` master for future releases on all steinemann machines

**Renamed !** library to  `CalmarProductSteinemann`

Releases after Q42024


## `2.0.2.x` branch releases for Concept4 WEU only machines

Only installable on `WEU Concept 4` machines. 
Envolved for WEU only with limited backwards compatiblity to the DMAX machine base. 
A merge has to be done to support the DMAX/MaxLiner with this code base --> use release 3.0.x

#### Changes

* CHG: how to position the PrintModule (fWorkerMasterPos, DetectToCam/CamToPrint)
* CHG: add local deformation calculation 
* CHG: moved some code to this library (UvLedModule, PowerControl, ExhaustSystem, `ST_ADS _Camera`, `ST_ADS_DVT_SHEETALIGNMENT`)
* CHG: improve some commends and logging
* CHG: moved some print specific code to `CalmarComponentsPrint`
* CHG: use latest `CalmarComponentsPrint` with support for new Jetmapping and the new BufferManagement for endless printing
* CHG: add `CamStarted()` and `CamDone()` callback on `I_CameraSink` 
* CHG: worker can run all in parallel mode and can support multiple attached CTs 
* ....



## `2.1.0` releases for DMAX/MaxLiner only

**Renamed !** library to `CalmarProductSteinemann`, but code stays on state of `2.0.1.x` bugfix releases. This is future branch for bugfix on DMAX/Maxliner machines

### `2.0.1.14` - release installed and tested machines: ...

#### Changes

* ADD:  `FB_SheetDetectSupervision`, `ST_SheetDetectSupervisionPar`
* CHG: `FB_PH.init()` according the change in CalmarCompPrint `2.0.4`
  * added `mJobPause` in `I_PrintStatusClient`
  * adapt to `printPrepare` interface change
  * adapt to changed tempmonitor interface
* CHG: use & adapt to Commons 1.5.14
* CHG: `FB_CameraTrigger`: `bI_SensorSupervisionEnable` added.
* CHG: adapt WorkerDefGrid.Abort() to be able to do an external abort on current attached CT
* CHG: Minor adaptation in `FB_CameraTrigger` reset fsm
* CHG: prepare abort possibilities on ContainerManager
* CHG: update StartShift factor to reach 80m/min production speed without missed print start
* CHG: default distance for CT verification & sheet eject
* CHG: deformation abort handling
* CHG: reset data in FB_PythonDeformation
* FIX: layers in _VISU_PH_Grid
* CHG: Abort deformation if requeted by py script
* CHG: commit machine state (updated library references, remove MAX_NB_PASSES overwrite)
* CHG: improve some VISUs (Better CamTrigger status, remove simulation from PrintOverview, show CT Details on request)
* CHG: BugFixes
* CHG: make it compatible with CompPrint >= `2.0.1.18` - remove `nCorrection` Input from `FB_PH` 
* FIX: hotfix version where the CONSTANTS (`MAX_BUFFER_SIZE` and `BUFFER_ITEM_SIZE`) of `FB_DeformationPointFifo` are not visible in the ADS Router.
       Added new fb outputs with the same data in it (`nBufferSize`, `nBufferItemSize`). Should be backwards compatible. Use the new once in the python script if you have ADS symbol not found errors.
* FIX: attempt to fix blocked worker in deformation script after invalid cam points improve abort handling and py ct release
* FIX: compiler warnings with I_Sim
* FIX: attempt to handle hanging camera trigger after fast machine stop

## `2.0.1` 28.07.2022

* release `2.0.1` created, tested on DMAX 305.704, DPST-1005

### changes `2.0.0.13` BRM

* CHG: add some more verbose logs in LineCamera for rx frame timing debug

### changes `2.0.0.12` BRM

* CHG: speed improvements
* CHG: DefGrid_WorkerDeformation can have multiple CTs attached
* CHG: auto-setup of WorkerPosition for DefGrid_WorkerCamera
* CHG: interaction with FB_ImageProcessing and Workers (Camera, Deformation)
* CHG: improve debugging and logging

### changes `2.0.0.9` HOA/BRM

* FIX: FB_CameraTrigger: correction for bReleaseInhibitTrigger

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

| Revnum | Description   | Start Val | Change at                                                                                                                                                                                                                |
| ------ | ------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `xx`   | major rev     | 1         | Changes with behavior and interface changes.<br>If you can't exchange the previous version with this one <br>(without ANY source code change in your product) <br>this new version shall be a new major revision number. |
| `yyy`  | minor rev     | 0         | Changes with code changes and interface extensions.                                                                                                                                                                      |
| `zzz`  | bugfix number | 0         | Changes with bugfixes.                                                                                                                                                                                                   |

> Polytype AG 2021 