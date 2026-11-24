# Hardware versioning

This file records every hardware version of the G5Fly STM32 board.
Released versions are immutable: any hardware change requires a new version (see GUIDELINES.md).

## Version overview

| Version | Directory | Git tag | Status | Date |
|---|---|---|---|---|
| v1 | `hardware/versions/v1` | `v1.0` | Validated | 2026-09 |

Status values:
- `Prototype`: manufactured, validation in progress
- `Validated`: tested and working as specified
- `Released`: validated and published for production
- `Obsolete`: replaced by a newer version

---

## v1 (current)

**Status:** Prototype
**KiCad project:** `hardware/versions/v1/kicad/`
**Production files:** `hardware/versions/v1/kicad/production/`

### Main features
- Septentrio mosaic-G5 GNSS receiver, dual MMCX antenna connectors (MAIN / AUX)
- STM32G473RCT6 microcontroller running AP_Periph (DroneCAN)
- TJA1462 CAN transceiver
- LIS2MDL magnetometer
- USB-C (USB 2.0 and power)
- JST-GH connectors: CAN (x2), GNSS UART, MCU I2C
- DF40 mezzanine connector for the NXP MR-MCXN-T1 Hub
- Removable extension (V-cut): 30.5 x 40 mm or 30.5 x 30.5 mm mounting pattern
- Antenna supply selectable with JP1 (3.3 V / 5 V)

### Manufacturing
- Prototype batch manufactured by JLCPCB in September 2026:
  5 bare PCBs and 2 assembled boards.
- PCB: 6 layers, FR-4, 1.6 mm, OSP finish.
- The production files in this directory match the manufactured boards,
  except for the silkscreen version marking (changed from "REV-2" to "V1").

### Assembly notes
- R30 and R31 (0 Ω, 0603, marked `SHUNT`) are not populated (DNP).
  Solder them by hand only if required: TODO (describe when and what they connect).
- JP1: solder the bridge matching the antenna supply (3.3 V or 5 V), see DESIGN.md.

### Known issues
- Some footprints and symbols still reference external libraries (EasyEDA, legacy libraries);
  see GUIDELINES.md.
- Some 3D models are missing from `hardware/common/3d_models/` (3D view incomplete;
  no impact on manufacturing).
- TODO: hardware issues found during testing.

### Validation
| Test | Result |
|---|---|
| Power-up (USB and external 5 V) | TODO |
| GNSS fix with mosaic-G5 | TODO |
| DroneCAN communication with an ArduPilot flight controller | TODO |
| Magnetometer | TODO |
| USB communication | TODO |
| Stacking on the MR-MCXN-T1 Hub (DF40) | TODO |

---

## Template for a new version

Copy this block above the previous version when creating a new one:

    ## vX

    **Status:**
    **KiCad project:** `hardware/versions/vX/kicad/`
    **Production files:** `hardware/versions/vX/kicad/production/`

    ### Changes from vX-1
    - Added:
    - Changed:
    - Fixed:
    - Removed:

    ### Manufacturing
    -

    ### Known issues
    -

    ### Validation
    | Test | Result |
    |---|---|