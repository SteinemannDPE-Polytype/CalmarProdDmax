# TODO list for library

- [ ] Refactor FB_LineCamera into one only FB with sName defined and in init() and a common sName property for specific fb
- [ ] Maxliner -> DMAX
- [ ] ST_ADS_FOIL used not available definition
- [ ] LineCamera one FB with configurable width (or size settings)
- [ ] Worker changes between DMAX and Jetliner, review structural changes
  - [ ] Maxliner seems to be wrong, we will name it again DMAX (which should be more common)
  - [ ] What did change on the configuration side for the PM and Workers?
    - [ ] MultiAttach
    - [ ] Distance configuration based on? Before SensorToCam, CamToPrintUnit, new from ModuleMaster
    - [ ] ...???