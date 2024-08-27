# Elementary Logic Gates Documentation

## 1. **NOT Gate**
- **Function**: Inverts the input signal (0 becomes 1, 1 becomes 0).
- **Truth Table**:

| Input (A) | Output (NOT A) |
|-----------|----------------|
|     0     |       1        |
|     1     |       0        |

- **Implementation**:
  - **Transistor-Based**: Use an NPN transistor. Input signal goes to the base, and the output is taken from the collector. The emitter is grounded.
  - **CMOS**: A CMOS inverter uses a PMOS and NMOS transistor pair. Input connects to both gates; the output is taken from their connection point.

## 2. **OR Gate**
- **Function**: Outputs 1 if any of the inputs are 1.
- **Truth Table**:

| Input (A) | Input (B) | Output (A OR B) |
|-----------|-----------|-----------------|
|     0     |     0     |        0        |
|     0     |     1     |        1        |
|     1     |     0     |        1        |
|     1     |     1     |        1        |

- **Implementation**:
  - **Diode Logic**: Connect the anodes of two diodes to the inputs, and tie their cathodes together. Connect a resistor between this junction and ground. The junction is the output.
  - **CMOS**: Two PMOS transistors in parallel with their sources tied to Vcc, and two NMOS transistors in series with their sources connected to ground. The output is taken from the connection point between the PMOS and NMOS.

## 3. **AND Gate**
- **Function**: Outputs 1 only if all inputs are 1.
- **Truth Table**:

| Input (A) | Input (B) | Output (A AND B) |
|-----------|-----------|------------------|
|     0     |     0     |         0        |
|     0     |     1     |         0        |
|     1     |     0     |         0        |
|     1     |     1     |         1        |

- **Implementation**:
  - **Diode Logic**: Use diodes in reverse bias connected to the inputs. The cathodes connect together to form the output.
  - **CMOS**: Two PMOS transistors in series with their sources connected to Vcc, and two NMOS transistors in parallel with their sources connected to ground. The output is taken from the connection point between the PMOS and NMOS.

## 4. **XOR Gate**
- **Function**: Outputs 1 if the inputs are different.
- **Truth Table**:

| Input (A) | Input (B) | Output (A XOR B) |
|-----------|-----------|------------------|
|     0     |     0     |         0        |
|     0     |     1     |         1        |
|     1     |     0     |         1        |
|     1     |     1     |         0        |

- **Implementation**:
  - **CMOS**: Four transistors are used. The gate works by combining an OR gate and an AND gate with a NOT gate.

## 5. **MUX (Multiplexer)**
- **Function**: Selects one of many input signals and forwards the selected input to a single output line.
- **Truth Table**: (For 2-to-1 MUX)

| Selector (S) | Input 0 | Input 1 | Output (Y) |
|--------------|---------|---------|------------|
|      0       |    A    |    B    |     A      |
|      1       |    A    |    B    |     B      |

- **Implementation**:
  - **CMOS**: Use transmission gates to pass the selected input to the output based on the control signals.

## 6. **DMUX (Demultiplexer)**
- **Function**: Takes a single input signal and routes it to one of several output lines.
- **Truth Table**: (For 1-to-2 DMUX)

| Selector (S) | Input (D) | Output 0 | Output 1 |
|--------------|-----------|----------|----------|
|      0       |     D     |     D    |     0    |
|      1       |     D     |     0    |     D    |

- **Implementation**:
  - **CMOS**: Use transmission gates to route the input to the selected output line based on the control signals.

## 7. **NOT16**
- **Function**: Inverts each bit of a 16-bit input.
- **Truth Table**: (For a single bit)

| Input (A) | Output (NOT A) |
|-----------|----------------|
|     0     |       1        |
|     1     |       0        |

- **Implementation**:
  - **CMOS**: Use 16 individual NOT gates to invert each bit of the 16-bit input.

## 8. **AND16**
- **Function**: Performs a bitwise AND operation on two 16-bit inputs.
- **Truth Table**: (For each bit)

| Input A | Input B | Output (A AND B) |
|---------|---------|------------------|
|    0    |    0    |        0         |
|    0    |    1    |        0         |
|    1    |    0    |        0         |
|    1    |    1    |        1         |

- **Implementation**:
  - **CMOS**: Use 16 individual AND gates to perform the bitwise AND operation on each pair of bits.

## 9. **OR16**
- **Function**: Performs a bitwise OR operation on two 16-bit inputs.
- **Truth Table**: (For each bit)

| Input A | Input B | Output (A OR B) |
|---------|---------|-----------------|
|    0    |    0    |        0        |
|    0    |    1    |        1        |
|    1    |    0    |        1        |
|    1    |    1    |        1        |

- **Implementation**:
  - **CMOS**: Use 16 individual OR gates to perform the bitwise OR operation on each pair of bits.

## 10. **MUX16**
- **Function**: Selects one of many 16-bit input signals and forwards the selected input to a single 16-bit output line.
- **Truth Table**: (For a single bit of each 16-bit line)

| Selector (S) | Input 0 | Input 1 | Output (Y) |
|--------------|---------|---------|------------|
|      0       |    A    |    B    |     A      |
|      1       |    A    |    B    |     B      |

- **Implementation**:
  - **CMOS**: Use 16 individual 2-to-1 MUXes for each bit of the input.

## 11. **OR18WAY**
- **Function**: Performs a logical OR operation on 18 inputs, outputting 1 if any input is 1.
- **Truth Table**: (Example for 3 inputs)

| Input 0 | Input 1 | Input 2 | Output (OR18WAY) |
|---------|---------|---------|------------------|
|    0    |    0    |    0    |        0         |
|    0    |    0    |    1    |        1         |
|    0    |    1    |    0    |        1         |
|    1    |    0    |    0    |        1         |
|    1    |    1    |    1    |        1         |

- **Implementation**:
  - **CMOS**: Chain OR gates together to handle all 18 inputs.

## 12. **MUX8WAY16**
- **Function**: Selects one of eight 16-bit input signals and forwards the selected input to a single 16-bit output line.
- **Truth Table**: (For each bit of the 16-bit lines)

| Selector (S2 S1 S0) | Input 0 | Input 1 | ... | Input 7 | Output (Y) |
|---------------------|---------|---------|-----|---------|------------|
|         000         |    A    |    B    | ... |    H    |     A      |
|         001         |    A    |    B    | ... |    H    |     B      |
|         ...         |   ...   |   ...   | ... |   ...   |    ...     |
|         111         |    A    |    B    | ... |    H    |     H      |

- **Implementation**:
  - **CMOS**: Use a combination of 16 8-to-1 MUXes, each controlled by the same selector signals.
