# M702D · Communication

Ward-Beck Systems M702D, 1996|29. Wiki page: [M702D on WBSps.ca](https://wardbecksystems.github.io/WBSps.ca/PAGES/M702D.html)

| Folder | What is in it | Files |
|---|---|---|
| [SCHEMATICS/](SCHEMATICS/) | electrical drawings: schematics, functional diagrams, component layouts, wiring | 1 |
| [MECHANICAL/](MECHANICAL/) | front panels, cover plates, metalwork, assemblies; the front panel as vectors | 0 |
| [PINOUTS/](PINOUTS/) | the RTO-144 connector: connection sheets, connector layouts, rear views | 2 |
| [MANUALS/](MANUALS/) | manuals, manual pages, price lists, brochures, documents | 1 |
| [PHOTOS/](PHOTOS/) | photographs of the module | 0 |
| [SOFTWARE/](SOFTWARE/) | program listings, firmware, the plugin | 0 |
| [KICAD/](KICAD/) | KiCad schematics traced from the drawings, the symbol, PCB projects | 2 |
| [OCR/](OCR/) | the note of every file: date, origin, title block, OCR text | 2 |

<!-- module data: tools/module_specs.py, tools/forum_quotes.py -->

## Specifications

From the technical data sheet: [1996 - M702D - file.wpd](MANUALS/1996%20-%20M702D%20-%20file.wpd) page 1 (read by OCR; check against the page). As data: [`Specifications.json`](Specifications.json).

| | |
|---|---|
| **Gain** | (Bridging) |
| **Speaker output** | +27 dB to +7 dB, ±1 dB. |
| **To line output** | +15 dB to -5 dB, ±1 dB. |
| **Frequency response** | ±1 dB from 100 Hz to 5 kHz. |
| **Noise** | Better than 80 dB below 1.5 watts or +18 dBm (gain set to unity for line output or +17 dBm for speaker output), 20 Hz to 20 kHz bandwidth. |
| **Harmonic distortion** | Less than 1% from 100 Hz to 5 kHz at +18 dBm output (balanced, or 1.5 watts) |
| **Input level** | +8 dBm nominal, +19 dBm maximum. |
| **Input impedance** | 10K ohms balanced and centre tapped. |
| **Source impedance** | 600 ohms or less, balanced. |
| **Output levels** |  |
| &nbsp;&nbsp;Line | +8 dBm nominal, +22 dBm maximum. |
| &nbsp;&nbsp;Speaker | 300 mW nominal, 3 watts peak power. |
| **Output impedance** |  |
| &nbsp;&nbsp;Line | Less than 30 ohms, balanced. |
| &nbsp;&nbsp;Speaker | Less than 1 ohm, unbalanced. |
| **Load impedance** |  |
| &nbsp;&nbsp;Line | 600 ohms or greater, balanced. |
| &nbsp;&nbsp;Speaker | 8 ohms, nominal. |
| &nbsp;&nbsp;Mounting |  |
| &nbsp;&nbsp;Full | 100 dB down. |
| &nbsp;&nbsp;Part | 6 dB to 24 dB down. |
| &nbsp;&nbsp;Override | Full output. |
| **Power requirements** | +32 volts DC unregulated. 45 mA idle, 350 mA maximum at 1.5 watts. |
| **Ambient temperature** | 0 to 40 degrees Celsius. |
| **Dimensions** | 0.7&quot; wide x 4.4&quot; high x 11.0 deep. (18 mm x 112 mm x 280 mm). |

## Circuit description

From [1996 - M702D - file.wpd](MANUALS/1996%20-%20M702D%20-%20file.wpd) page 1 (read by OCR; check against the pages). As data: [`CircuitDescription.json`](CircuitDescription.json).

<details><summary>Read it</summary>

The M702D Output Amplifier is designed to receive a +8 dBm nominal input signal and amplify it to a power level sufficient to operate aloud speaker to a maximum of 3 watts.

Input The input is applied to pins U and V of the module connector and is coupled by C201 and C202 to two separate resistive networks followed by two solid state switches. The switches provide two individual signal paths between the module input and the buffer and output amplifiers U203 and U204. The lower path is used to produce full output, while the upper path will produce a partially muted output. The control logic determines the choice of the signal path used for any given operational conditions.

Mute Control Logic Pins 18, 19 and 20 of the module connector serve as the control inputs to the logic gates U202A through D.

Under normal conditions, with no ground applied to any of the three control inputs, the Band D sections of U201 are switched on and theA and C sections are off. As a result, the amplifier is operating at full output (no muting applied).

If the mute input (pin 19) is grounded, sections Band D of U201 are off, blocking the main signal path. At the same time, sections A and C of U201 are on, opening the part mute path. The amount of muting is determined by R217, and is adjustable over a 20 dB range.

When pin 20 is grounded, it will override both full mute and part mute functions as described above. The results in full output via the Band D sections of U201.

Output The audio signal from the output of the solid state switches within U201 is coupled through C207 and C208 to U203 and the power output stage built around U204.

Integrated circuit U204, along with Q203, Q204, Q205 and Q206 plus associated components are configured as a 3 watt power booster stage for driving an 8 ohm speaker load. Its output appears at module connector pins 21 andY.

An actively balanced +8 dBm, 600 ohm output is derived between U203B and U204. This is available at the module connector pins Wand X. This output is capable of driving a single 600 ohm load.

R250 controls the amount of negative feedback applied to U203B. This serves as again trim control, allowing ±10 dB adjustment range from the nominal system level of +8 dBm, or 300 mW respectively.

Power Supply Decoupling The module is powered by a +32 volt DC unregulated power source, connected to pins 13 and P of the module connector. After passing through an isolation diode (CR205), and a fuse (F201), the supply voltage is decoupled by R235, C212 and C213. DS201 serves as a visual power indicator.

Q202 provides further filtering and reduces the supply voltage to 12 volts to operate U201 and U202.

Under idle conditions, the M702D draws approximately 45 mA, rising to 350 mA at 3 watt output. With the output shorted, the current will rise to approximately 750 mA.

A short circuit condition at the amplifier output will not normally blow fuse F201, as long as the amplifier is operating with normal program material. However, sustained full output into a short circuit failure will cause the fuse to open.

C201 Capacitor 1 uF/35 V ITT 1M35 C202 &quot; 1 uF/35 V &quot; &quot; C203 &quot; 0.1 uF/35 V &quot; 0.1M35 C204 &quot; 0.1 uF/35 V &quot; &quot; C205 &quot; 0.1 uF/35 V &quot; &quot;

C206 &quot; 0.1 uF/35 V &quot; &quot; C207 &quot; 22 uF/25 V Philips 03016229 C208 &quot; 22 uF/25 V &quot; &quot; C209 &quot; 22 uF/25 V &quot; &quot; C210 &quot; 47 pF &quot; 638-34479

C211 &quot; 22 uF/25 V &quot; 03016229 C212 &quot; 220 uF/40 V &quot; 03217221 C213 &quot; 220 uF/40 V &quot; &quot; C214 &quot; 0.1 uF/50 V Aselco CQ92-MC-100-153M C215 &quot; 10 uF/25 V ITT 10M25

C216 &quot; 22 uF/25 V Philips 03016229 C217 &quot; 47 pF &quot; 638-34479 C218 &quot; 100 pF &quot; 638-58101 C219 &quot; 22 uF/25 V &quot; 03016229 C220 &quot; 100 uF/25 V &quot; 03116101

C221 &quot; 100 uF/25 V &quot; &quot; C222 &quot; 680 uF/16 V &quot; 03215681 C223 &quot; 10 uF/25 V ITT 10M25 C224 &quot; 10 uF/25 V &quot; &quot; C225 &quot; 0.068 pF Aselco CQ92-MC-100-802M

C226 &quot; 22 uF/25 V Philips 03016229 C227 &quot; 0.1 uF/50 V Aselco CQ92-MC-100-153M C228 &quot; 100 pF &quot; 638-58101 C229 &quot; 100 pF &quot; &quot;

**C230 &quot; SOT**

C231 &quot; 47 pF &quot; 638-34479 C232 &quot; 22 uF/25 V Philips 03016229

CR201 Diode Motorola 1N4148

**CR208 &quot; &quot; 1N4148**

CR209 Diode Motorola 1N4148

**CR212 &quot; &quot; &quot;**

DS201 LED, Yellow Dialight 555-2401

F201 Fuse Amp AGC.500

Q201 Transistor National PN3569

**Q206 &quot; &quot; TIP29**

R201 Resistor 1/4W 5% 15K Philips CR25

**R216 &quot; &quot; 1K &quot; &quot;**

R217 Potentiometer 20K Piher PT10H 20K R218 Resistor 1/4W 5% 1K Philips CR25

**R225 &quot; &quot; 47K &quot; &quot;**

R226 Resistor 1/4W 5% 100K Philips CR25

**R234 &quot; 1/2W 5% 4K7 &quot; SFR25 HJ**

R235 &quot; 5W 5% 10 Dale CW-5-5

R236 &quot; 1/4W 5% 4K7 Philips CR25

**R245 &quot; &quot; 6K2 &quot; &quot;**

R246 &quot; 3W 5% 1.5 Dale CW-2B R247 &quot; 1/4W 5% 27 Philips CR25

**R248 &quot; 1/2W 5% 2.2 &quot; SFR25 HJ**

R249 &quot; 3W 5% 27 Dale CW-2B R250 Potentiometer 20K Piher PT10H 20K

R251 Resistor 3W 5% 1.5 Dale CW-2B R252 &quot; 1/4W 5% 1K Philips CR25

**R260 &quot; &quot; 100 &quot; &quot;**

U201 Integrated Circuit National CD4016CN

</details>

<!-- /module data -->

## KiCad

_KiCad: a schematic (`.kicad_sch`) traced from each electrical drawing, the module symbol (`.kicad_sym`) and its PCB projects. Traced schematics are the line work only: redraw with symbols over them._

- [M702D.kicad_sym](KICAD/M702D.kicad_sym)
- [PCB M702D](KICAD/PCB%20M702D)

---
Archive: Anthony Peter Kuzub · [WBSps.ca](https://WBSps.ca) · [WBSps.Kuzub.com](https://WBSps.Kuzub.com)
