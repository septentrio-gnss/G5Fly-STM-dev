# Hardware versioning

This file lists every hardware version of the G5Fly STM board.
A released version never changes: any hardware change requires a new version (see [GUIDELINES.md](GUIDELINES.md)).

| Version | Directory | Git tag | Status | Date |
|---|---|---|---|---|
| v1 | [`hardware/versions/v1`](hardware/versions/v1) | `v1.0` | Validated | 2026-09 |

Status values: 
- `Prototype` (validation in progress)
- `Validated` (tested and working)
- `Released` (published for production)
- `Obsolete` (replaced)

---

## v1 (current)

**Status:** Validated

### Main features
- 30.5 x 30.5 mm FPV mounting pattern, with a removable V-cut extension (30.5 x 40 mm)
- Septentrio mosaic-G5 GNSS receiver, dual MMCX antenna connectors (MAIN / AUX)
- STM32G473RCT6 running AP_Periph (DroneCAN), TJA1462 CAN transceiver
- LIS2MDL magnetometer
- USB-C (USB 2.0 and power)
- JST-GH connectors: CAN (x2), GNSS UART, MCU I2C
- Antenna supply selected with JP1 (3.3 V or 5 V)
- DF40 connector for the NXP MR-MCXN-T1 hub

### Manufacturing
- JLCPCB, September 2026: 5 bare PCBs and 2 assembled boards
- 6-layer FR-4, 1.6 mm, OSP finish

### Assembly notes
- R30 and R31 (0 Ω, marked `SHUNT`) are not populated.
- JP1: solder the bridge for the antenna supply voltage (see [DESIGN.md](DESIGN.md)).

### Known issues
- Some footprints and symbols still come from external libraries (EasyEDA, legacy).
- Some 3D models are missing (3D view only, no impact on manufacturing).

## Template for a new version

Copy this block above the previous version:

    ## vX

    **Status:**

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
    Test results: `hardware/versions/vX/G5Fly_STM_test_plan.xlsx`