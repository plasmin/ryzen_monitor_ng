# Version 2.2.0
- Added experimental support for Zen4 Raphael desktop processors (Ryzen 7000 series)
  - 1-CCD: 7800X3D, 7700X, 7700, 7600X3D, 7600X, 7600, 7500F, etc.
    (PM tables 0x540100–0x540108)
  - 2-CCD: 7950X, 7950X3D, 7900X, 7900X3D, 7900, etc.
    (PM tables 0x540000–0x540005)
- Zen4 per-core arrays mapped via dump analysis (1-CCD) and extrapolated (2-CCD)
- CPU SVI2 power computed from voltage × current when not provided by PM table
- EDC limit/percentage display for Zen4
- FIT display hidden for Zen4 (not present in Raphael PM tables)
- L3 cache display supports multi-CCD with NULL safety

# Version 2.1.1
- Updated libsmu for ryzen_smu v0.1.7 compatibility (amkillam fork)
- Fixed driver version check to support newer SMU interfaces
- Simplified SMU initialization for Zen4 MP1 IF v11

# Version 2.1.0
- Hide display for NaN or zero-valued fields
- Added V_VDDM, IO_VDDCR_SOC_POWER and IOD_VDDIO_MEM_POWER display
- Added support for Matisse single-CCD SKUs (3600/X, 3700X, 3800X/XT)
- Updated PM table 0x240903 for Matisse

# Version 2.0.5
- New sysinfo routine
- Command line switch to print debug init information

# Version 2.0.4
- Fix for PM hack
- Enabled the disabled cores hack also for reading a dump
- Fix EDC in export when not available from PM table

# Version 2.0.3
- Fix version number
- Fix fake fuse hack

# Version 2.0.2
- Hack to create fake fuse for Family 17h Model 18h (Picasso Athlon 300U)

# Version 2.0.1
- Fixes for Picasso PM table 0x1E0004

# Version 2.0.0
- Added support for Cezanne disabled cores fuse (thx @PJVol)
- Added support to show Curve Optimizer counts
- Added support for exporting metrics to a named pipe using Influx DB line protocol format for telegraf import with tail plugin
- Fixed missing free for SMU obj
- Added support for set and get values; CO counts, PPT, PPTFast, PPTAPU, TDC, TDCSoC, EDC, EDCSoC, STAPM Limit & Time, PPT Time, THM Limit, Scalar, OCMode, Eco, MaxPerf
- Added argparse library
- Added make install and debug target
- Added keystrokes in monitor: q - quit, c - compact view, i - toggle info, e - toggle electrical, o - toggle counts, m - toggle memory, g - toggle gfx, p - toggle power
- Added command line switches to control view toggles
- Added write to dumpfile
- Added dump PM table to screen
- Added tentative support for Lucienne/Renoir PM tables (0x370003, 0x370005)
- Added tentative support for Picasso PM tables (0x1E0004)
- RyzenSMU library updated to v0.1.4 (not yet merged at this time, https://gitlab.com/mann1x/ryzen_smu)
- Fixed average/peak core_voltage calculation (SMU max core voltage seems to be broken in some conditions)