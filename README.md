# Logical Sizing and Delay Optimization

This project focuses on the design, optimization, and layout of a 3-stage logic path to minimize propagation delay. The primary objective is to apply the principles of logical effort for transistor sizing and to verify the results through schematic and post-layout simulations.

## Project Description

The logic path under consideration consists of four gates: an inverter, a NAND gate, a NOR gate, and a final inverter. The goal is to minimize the delay from the input of the first inverter to the output of the NOR gate. The final inverter acts as a load.

## Methodology

1.  **Logical Effort:** The method of logical effort was employed to estimate the optimal sizes of the transistors in the NAND and NOR gates. This technique provides a systematic way to size transistors in a multi-stage logic network to achieve the minimum possible delay.

2.  **Transistor Sizing:** Based on the logical effort calculations, the sizes of the PMOS and NMOS transistors in the NAND and NOR gates were determined. The goal was to make the effort delay of each stage equal.

3.  **Schematic Simulation:** The designed circuit was simulated using HSPICE to measure the high-to-low (tpHL) and low-to-high (tpLH) propagation delays.

4.  **Layout Design:** A physical layout of the circuit was created using the Virtuoso Layout Editor from Cadence, with standard cells from the TSMC 16nm library. The calculated transistor sizes were mapped to the available standard cell sizes.

5.  **Verification:** Design Rule Checking (DRC) and Layout Versus Schematic (LVS) checks were performed using Calibre to ensure the layout was physically correct and matched the schematic.

6.  **Post-Layout Simulation:** After successful verification, the netlist was extracted from the layout, including parasitic capacitances. This netlist was then simulated again in HSPICE to obtain more accurate delay measurements.

## Results

The following results were achieved:

*   **Optimal Transistor Sizes (calculated):**
    *   NAND gate (WN2): ~42 Fins
    *   NOR gate (WN3): ~33 Fins
*   **Post-Layout Simulation Delays:**
    *   tpHL: 17.218 ps
    *   tpLH: 19.782 ps

## Conclusions and Learnings

*   The project successfully demonstrated the effectiveness of the logical effort method in minimizing the delay of a multi-stage logic path.
*   The difference between the tpHL and tpLH values can be attributed to the stacking effect of transistors and the different mobilities of electrons and holes.
*   The process of mapping calculated transistor sizes to the discrete sizes available in a standard cell library introduces a level of approximation that can affect the final delay values.
*   This project provided hands-on experience with industry-standard EDA tools such as HSPICE for simulation, Virtuoso for layout, and Calibre for verification.
