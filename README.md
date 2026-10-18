# Siemens S7-300 Motor Control with WinCC HMI

Motor control and HMI work developed during an internship at **OCP Jorf Lasfar**. This repository documents physical Siemens equipment, a TIA Portal Ladder Diagram (LAD) control program, and a WinCC operator interface.

## Physical setup

The internship photographs show a Siemens PLC cabinet with physical controls, a **SITOP PSU100M** power supply, interface relays, and a **SIMATIC HMI**. These photos provide physical context for the work; the cabinet is not presented as an exact module-for-module match to the TIA Portal rack view below.

![Siemens PLC cabinet and physical controls](picture_material_software/PLC_setup.jpeg)

![SITOP PSU100M and interface relays](picture_material_software/power_source_and_interface_relays.jpeg)

![Physical SIMATIC HMI](picture_material_software/HMI.jpeg)

## PLC configuration

The TIA Portal rack configuration uses a **SIMATIC S7-300 CPU 315-2 DP** with a **CP 341 RS422/485**, **CP 343-1 Lean**, **DI 16 × 24 VDC**, and **DO 16 × 24 VDC**.

![S7-300 rack configuration in TIA Portal](picture_material_software/hardware_configuration.png)

## Control logic

- Three mutually exclusive start modes: **INSTANT**, **10 s**, and **15 s**. The delayed modes use TON timers before the motor run command is set.
- **START** and **STOP** commands with an SR latch for the run command.
- Fault blocking and status indication for running, stopped, and fault conditions.

![Start and stop logic with SR latch](picture_material_software/ladder_start_stop.png)

![TON timers for the 10 s and 15 s modes](picture_material_software/ladder_timers.png)

![Status and fault indication logic](picture_material_software/ladder_status_fault.png)

## Operator interface

The physical HMI above and the **WinCC simulator** screen below show mode selection, START/STOP controls, and motor status and fault indicators.

![WinCC HMI simulator](picture_material_software/wincc_hmi.png)

The images document the control concept and interface; they do not serve as a commissioning record or establish production deployment.
