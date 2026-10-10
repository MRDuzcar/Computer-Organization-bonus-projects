# Digital Logic Breadboard Projects

Four hands-on projects completed for EECS 2021 Computer Organization at York University during Summer 2026. I built the circuits on breadboards using logic ICs, documented their wiring and operation, and checked outputs against expected binary results. The first three projects also include Falstad simulations.

The projects cover combinational arithmetic, decoding, and sequential logic. Full reports contain circuit diagrams, breadboard photographs, and example results.

## Projects

| Project | Implementation | Demonstrated behavior |
|---|---|---|
| 4-bit adder/subtractor | XOR, AND, and OR gates with cascaded carry logic | Selectable binary addition and subtraction |
| 3×3 binary multiplier | Partial-product AND gates and gate-built half/full adders | Multiplication of two 3-bit inputs with a 6-bit output |
| 2-to-4 decoder | NAND gates only | One selected output for each 2-bit input combination |
| 4-bit ripple counter | JK flip-flops and an adjustable 555 timer clock | Binary counting with LED outputs and adjustable counting speed |

## 1. 4-Bit Adder/Subtractor

**Completed:** May 2026

Built a four-stage arithmetic circuit using basic XOR, AND, and OR gates rather than dedicated full-adder ICs. Each stage produces a sum bit and passes its carry to the next stage.

A shared subtraction control signal selects the operation:

- **SUB = 0:** Compute A + B.
- **SUB = 1:** Invert the B inputs and set the initial carry-in to 1, computing A + NOT(B) + 1 for two's-complement subtraction.

The report traces `1001 − 0001 = 1000` (9 − 1 = 8) through the individual stages and shows the breadboard result.

[Read the adder/subtractor report](4%20Bit%20adder%20-%20Subtractor.pdf)

## 2. 3×3 Binary Multiplier

**Completed:** June 2026

Built a combinational multiplier for two unsigned 3-bit numbers. AND gates generate partial products, which are combined using half-adders and full-adders built from basic logic gates. The circuit produces a 6-bit product, covering the maximum input case of 7 × 7 = 49.

The documented breadboard examples are:

| Inputs | Decimal product | Expected 6-bit binary output |
|---|---:|---|
| 7 × 7 | 49 | `110001` |
| 3 × 7 | 21 | `010101` |
| 5 × 5 | 25 | `011001` |

The report includes the reference schematic, a Falstad simulation, and photographs of the partial-product and adder wiring. The reference schematic is credited to electricaltechnology.org in the report.

[Read the multiplier report](3x3%20binary%20multiplier.pdf)

## 3. 2-to-4 Decoder Using NAND Gates

**Completed:** July 2026

Built a decoder using NAND gates to generate input inversions and four active-HIGH decoded outputs. Two inputs select one of four LEDs.

The breadboard uses three quad two-input NAND ICs, a 5 V supply, input pull-down resistors, and LED current-limiting resistors. The report shows all four input combinations:

| A | B | Selected output |
|---|---|---|
| 0 | 0 | I0 |
| 0 | 1 | I1 |
| 1 | 0 | I2 |
| 1 | 1 | I3 |

[Read the decoder report](2x4%20Decoder%20with%20NAND.pdf)

## 4. 4-Bit Binary Ripple Counter

**Completed:** July 2026

Built a four-bit counter using SN74HC112N JK flip-flops driven by an SA555P timer. With J and K held HIGH, each flip-flop toggles on its active clock edge. Each stage clocks the next, forming a ripple counter with four LED bit indicators.

A potentiometer adjusts the timer's clock frequency and therefore the counting speed. The counter cycles through 16 binary states, from `0000` to `1111`, before repeating.

In the timer oscillator, TRIG and THRES are connected to monitor the same timing capacitor voltage. They use different comparison thresholds: TRIG compares against half of CONTROL, while THRES compares against CONTROL. With the default internal references, these correspond to approximately one-third and two-thirds of the supply voltage.

[Read the counter report](4-bit%20binary%20counter.pdf)

[Watch the demonstration](https://drive.google.com/file/d/1D7bTK9Uz6o6VsKHJTn4yKfiw7pryZu5W/view?usp=sharing)

## Skills Demonstrated

- Breadboard construction and logic IC wiring.
- Gate-level implementation of arithmetic and decoding circuits.
- Carry propagation and partial-product addition.
- JK flip-flop operation and asynchronous binary counting.
- Adjustable clock generation using a 555 timer.
- Falstad simulation and comparison of expected and observed outputs.
- Circuit documentation with diagrams and annotated photographs.

## Notes on the Original Reports

The PDFs are the original coursework reports. Two wording corrections apply:

- The multiplier introduction mentions addition and subtraction; the project performs multiplication using gate-built adders to combine partial products.
- The counter report gives conflicting descriptions of the 1 kΩ resistor connection at timer pin 7. The earlier wiring list and diagram show this resistor connected to +5 V, not ground. Consult the complete schematic when reproducing the timer circuit.

## AI Assistance

AI tools assisted with preparing this repository’s README. The circuit construction, simulations, testing, and original project reports are my own work.
