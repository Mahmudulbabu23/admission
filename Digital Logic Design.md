## Practice Questions — Digital Logic Design

### 1) Number Systems & Conversions
**Question:** Convert (7B.3)₁₆ to binary and decimal. Also express 173.375₁₀ in hexadecimal.
**Solution:**
- 7 → 0111, B → 1011, 3 → 0011 ⇒ (7B.3)₁₆ = 0111 1011.0011₂.
- Decimal: 7×16¹ + 11×16⁰ + 3×16⁻¹ = 112 + 11 + 0.1875 = 123.1875₁₀.
- 173.375₁₀ → hex: integer 173₁₀ = AD₁₆; fraction 0.375×16 = 6.0 ⇒ (AD.6)₁₆.

### 2) Boolean Algebra Identities
**Question:** Simplify F = (A + B)(A + B̅C) using Boolean algebra laws only.
**Solution:**
F = (A + B)(A + B̅C) = A + BB̅C + B A = A + 0 + AB = A + AB = A(1 + B) = A.

### 3) Karnaugh Map Minimization
**Question:** Minimize F(A,B,C,D) with minterms Σm(0,2,3,5,6,7,8,10,14,15).
**Solution:** Optimal SOP: F = A̅C̅ + A̅BD + AC + B̅CD̅.

### 4) Combinational Design — Adder/Subtractor
**Question:** Design a 4-bit adder/subtractor using a 4-bit ripple-carry adder and one control input M (0=add, 1=subtract). Describe the logic.
**Solution:** XOR each B bit with M, feed into RCA; set carry-in C₀ = M. Sum = A + (B ⊕ M) + M, which yields A+B when M=0 and A−B in two’s complement when M=1.

### 5) Code Conversion
**Question:** Design a combinational circuit to convert 4-bit BCD (valid 0000–1001) to Excess-3 code. Give minimized expressions.
**Solution:**
Let inputs D,C,B,A (D MSB). Excess-3 outputs W,X,Y,Z. Simplified (excluding invalid BCDs):
W = D + (C·B) + (C·A)
X = C̅B + C A̅ + C̅A
Y = B̅A + B A̅
Z = A̅

### 6) Multiplexer-Based Realization
**Question:** Implement F(A,B,C,D) = Σm(1,3,4,5,7,9,13) using a 4-to-1 MUX with select lines C,D.
**Solution:** Group by CD:
- CD=00 → terms with m1,4 → when CD=00, A̅B.
- CD=01 → m5,13 → when CD=01, A.
- CD=10 → m3 → when CD=10, A̅B̅.
- CD=11 → m7,9 → when CD=11, B.
Connect selects S₁=C, S₀=D; data inputs I0=A̅B, I1=A, I2=A̅B̅, I3=B.

### 7) Decoder Application
**Question:** Using a 3-to-8 decoder and minimal gates, realize F(A,B,C) = Σm(1,2,5,6).
**Solution:** Enable decoder; OR minterm outputs Y1, Y2, Y5, Y6 to form F.

### 8) Flip-Flop Characteristic Derivations
**Question:** Derive D and T excitation equations from JK flip-flop inputs.
**Solution:**
D = JQ̅ + K̅Q. T = JQ̅ + KQ.

### 9) Sequential Analysis
**Question:** A JK flip-flop has J = X̅Y, K = XY̅. Given present state Qₙ, find next state Qₙ₊₁ and describe behavior.
**Solution:** J is 1 only when X=0,Y=1; K is 1 only when X=1,Y=0; otherwise J=K=0. Thus Q toggles only when X≠Y, biased to follow Y: truth table shows Qₙ₊₁ = Y.

### 10) Counter Design
**Question:** Design a modulo-10 synchronous counter using JK flip-flops. Provide next-state equations conceptually.
**Solution:** Use 4 JK FFs (Q3 Q2 Q1 Q0). Drive with common clock. Use Karnaugh maps from count 0000–1001 then reset to 0000. Typical minimal excitations: J0=K0=1; J1=K1=Q0; J2=K2=Q0·Q1; J3=Q0·Q1·Q2, K3=1 with asynchronous clear when reaching 1010.

### 11) FSM Design — Sequence Detector
**Question:** Design a Mealy machine that detects overlapping pattern 1011 on serial input X and outputs Z=1 when seen. Provide state diagram description.
**Solution:** States S0(start), S1(1), S2(10), S3(101). Transitions: from S0 on 1→S1 else S0; S1 on 0→S2, on1 stay S1; S2 on1→S3 else S0; S3 on1→S1 with Z=1, on0→S2 with Z=0.

### 12) Timing and Hazards
**Question:** Explain static-1 hazard in SOP implementations and give a fix for F = A̅B + AB.
**Solution:** Adjacent 1-cells not covered by a common implicant can glitch low during input transitions. Add consensus term A̅B + AB + B = B to remove hazard; or implement as single implicant B using K-map grouping.

### 13) Propagation Delay Calculation
**Question:** A 4-bit ripple-carry adder uses full adders with 3 ns gate delay each. Estimate worst-case carry propagation delay and sum availability.
**Solution:** Carry chain traverses 4 FAs → 4×3 ns = 12 ns. MSB sum available after its own internal delay; if sum depends on carry-in, worst-case ~12 ns + 3 ns = 15 ns.

### 14) Programmable Logic Devices
**Question:** Compare ROM, PLA, and PAL in terms of programmability and typical use.
**Solution:** ROM: fixed OR array, programmable AND via address → good for truth-table storage. PLA: programmable AND and OR → most flexible, higher cost/delay. PAL: programmable AND, fixed OR (with limited fan-in) → faster/cheaper than PLA, less flexible.

## Topic-Wise Question Bank (20 each)

### Number Systems and Codes (20)
1. Convert 101101.011₂ to octal and decimal.
2. Convert 3AF.9₁₆ to binary and decimal.
3. Express 725.375₈ in binary and hexadecimal.
4. Add 110110₂ + 101011₂ and show carry.
5. Subtract 10101₂ from 100000₂ using 2's complement.
6. Convert −45₁₀ to 8-bit sign-magnitude, 1's complement, and 2's complement.
7. Represent +65 and −65 in excess-64 code.
8. Detect overflow when adding 01100101₂ and 01011110₂ in 2's complement.
9. Convert 8421 BCD 1001 0100 to Excess-3 and Gray code.
10. Convert Gray 11011 to binary.
11. Show how to detect invalid BCD codes with minimal logic.
12. Encode the decimal digits 0–9 into 7-seg active-low outputs.
13. Compute the Hamming distance between 101010 and 111000.
14. Design odd parity generator for 4-bit data.
15. Encode 8 inputs into 3-bit binary using an 8-to-3 priority encoder truth table.
16. Convert 0.1₂ repeating to decimal up to 5 places; explain non-terminating fraction.
17. Multiply 1101₂ by 101₂ (binary multiplication).
18. Divide 111010₂ by 101₂ (binary division) and show quotient and remainder.
19. Convert 999₁₀ to base-7 and base-12.
20. Show that Gray code is single-bit change per step; give a counterexample if you reorder bits.

#### Solutions — Number Systems and Codes
1) 101101.011₂ = 55.3₈; decimal 45.375₁₀.
2) 3AF.9₁₆ → binary 0011 1010 1111.1001₂; decimal 943.5625₁₀.
3) 725.375₈ → binary 111010101.011111101₂; ≈ 3A5.7E8₁₆ (truncated); decimal ≈ 469.4941.
4) 110110₂ + 101011₂ = 1 100001₂ (97₁₀).
5) 100000₂ − 10101₂ = 001011₂ (11₁₀) via 2's complement.
6) +45 = 00101101; sign-magnitude −45 = 10101101; 1's comp = 11010010; 2's comp = 11010011.
7) Excess-64: +65 → 10000001₂; −65 not representable in 8-bit excess-64 (would need −1 → 9 bits 111111111).
8) 01100101₂ + 01011110₂ = 11000011₂; signs positive → result negative ⇒ signed overflow.
9) BCD 1001 0100 → Excess-3 = 1100 0111; Gray of 10010100₂ = 11011100.
10) Gray 11011 → binary 10010₂ (18₁₀).
11) Invalid-BDC detector: Invalid = D + (C·B).
12) 7-seg active-low hex codes (a–g): 0=C0,1=F9,2=A4,3=B0,4=99,5=92,6=82,7=F8,8=80,9=90 (hex).
13) Hamming distance = 2.
14) Odd-parity bit P = ~(D3 ⊕ D2 ⊕ D1 ⊕ D0).
15) Priority encoder: outputs binary of highest 1; V flag = OR of all inputs.
16) 0.11111₂ ≈ 0.96875; 0.\bar{1}₂ → limit 1.0₁₀.
17) 1101₂ × 101₂ = 1000001₂ (65₁₀).
18) 111010₂ ÷ 101₂ → quotient 1011₂ (11₁₀), remainder 011₂ (3₁₀).
19) 999₁₀ = 2625₇ = 6B3₁₂.
20) Gray changes one bit because G = B ⊕ (B >> 1); reordering bits breaks adjacency (counterexample: swap bits yields two-bit jumps).

### Boolean Algebra, K-Maps, and Simplification (20)
1. Prove absorption: X + XY = X using a truth table.
2. Simplify F = A'BC + ABC + AB'C.
3. Simplify F = (A + B)(A + C)(B + C) to minimal SOP.
4. Use De Morgan's law to complement F = (A + BC')D'.
5. Derive canonical SOP and POS for F(A,B,C) = Σm(1,3,4,6).
6. Minimize F(A,B,C,D) = Σm(0,2,5,6,8,10,13,14) using a 4-variable K-map.
7. Identify essential prime implicants for the above F.
8. Minimize F with don't-cares d(1,3,7,11) for Σm(0,2,5,8,10,15).
9. Use Quine–McCluskey on F = Σm(0,1,2,5,6,7,8,9,10,14).
10. Detect static-1 hazard in F = A'B + AB'.
11. Add consensus terms to eliminate the hazard in Q10.
12. Show POS form for F = Σm(1,2,5,7).
13. Prove distributive law: X(Y + Z) = XY + XZ via algebra and truth table.
14. Factor F = AB + AC + AD to use a 2-level NAND-NAND implementation.
15. Derive XOR as minimal SOP and POS.
16. Express XNOR using only NAND gates.
17. Show how NAND is functionally complete using two small examples.
18. Convert a 3-level SOP to 2-level NAND implementation.
19. Compare gate counts for SOP vs POS for F = Σm(0,1,2,5,7).
20. Explain why don't-cares help reduce hazards.

#### Solutions — Boolean Algebra, K-Maps, and Simplification
1) Truth table shows X + XY equals X for all rows.
2) F = AC + AB'C.
3) Majority form: AB + AC + BC.
4) F' = A' (B' + C) + D.
5) SOP Σm(1,3,4,6); POS ΠM(0,2,5,7).
6) K-map ⇒ F = C D' + B' C' D' + B C' D.
7) Essential prime implicants: C D', B' C' D', B C' D.
8) With d(1,3,7,11), minimal SOP: F = C' + AD'.
9) Quine–McCluskey yields F = C D' + B' C' + A'C + AB.
10) Static-1 hazard when A and B toggle; paths not covered jointly.
11) Add consensus term AB to F = A'B + AB' to get A'B + AB' + AB (hazard-free).
12) POS: ΠM(0,3,4,6).
13) Algebra and truth table both match: XY + XZ.
14) F = A(B + C + D); NAND–NAND via double negation.
15) XOR SOP: A'B + AB'; POS: (A + B)(A' + B').
16) XNOR = (A NAND B)' can be built from 4 NANDs; or (A NAND A) NAND (B NAND B) NAND (A NAND B).
17) Show NOT with A NAND A; show AND via double NAND, OR via De Morgan.
18) Replace AND/OR with NAND + inversion bubbles to reach 2-level NAND.
19) SOP vs POS gate counts depend on fan-in; for this F, SOP typically fewer gates.
20) Don't-cares allow larger implicants → fewer terms and sometimes cover hazard-prone adjacencies.

### Combinational Building Blocks (20)
1. Design a 4:1 MUX from 2:1 MUXes only.
2. Implement F(A,B,C) = Σm(1,3,5,6) using a single 8:1 MUX with select ABC.
3. Build a 1-of-10 decimal decoder using two 3-to-8 decoders and gates.
4. Use a priority encoder to detect the highest-order 1 among 8 inputs; define tie behavior.
5. Design a 4-bit magnitude comparator using basic gates.
6. Realize a 7-seg decoder for hex digits; specify for inputs A–F.
7. Convert BCD to 9's complement using combinational logic.
8. Build a parity checker for 8-bit data using two 4-bit parity blocks.
9. Design a simple voting circuit that outputs 1 if at least 2 of 3 inputs are 1.
10. Implement a majority-of-5 circuit with minimal gates.
11. Use a MUX to implement a given truth table (provide mapping steps).
12. Design a lock/unlock combinational logic with four switches requiring 1010 pattern.
13. Show how to cascade two 4:1 MUXes to make an 8:1 MUX.
14. Create a combinational circuit that outputs 1 only for prime BCD digits.
15. Design a segment-blanking circuit that turns off display for leading zeros.
16. Implement a 3-bit even-odd detector with one XOR gate and buffering.
17. Design a binary-to-Gray converter and verify mapping.
18. Design a Gray-to-binary converter and verify mapping.
19. Describe hazards when decoding 2:4 with asynchronous inputs and propose fix.
20. Show how to realize any Boolean function with a PLA block; sketch connections.

#### Solutions — Combinational Building Blocks
1) Cascade three 2:1 MUXes: first stage selects between pairs, second stage selects final.
2) Map minterms to MUX data lines per ABC select; load 1 on I1,I3,I5,I6.
3) Use 3-to-8 for lower lines and another for enable on upper; gate outputs to 10 lines.
4) Priority encoder outputs index of highest 1; tie → highest-priority wins.
5) Comparator: (A3=XOR/BOR) chain; outputs GT = A>B, LT, EQ via subtract or bitwise cascade.
6) Use standard hex 7-seg truth table (0–F).
7) 9's complement = 1001 − digit; implement per bit with borrow chain or LUT.
8) Two 4-bit parity (XOR trees) then XOR their results.
9) Majority-of-3 = AB + AC + BC.
10) Majority-of-5 = sum≥3; minimal SOP from K-map (e.g., 10 implicants).
11) Load truth table rows into MUX data inputs; selects are variables.
12) AND pattern equality with switches; output high only on 1010.
13) Use one MUX for lower four inputs feeding second-stage 2:1 select on MSB.
14) Prime detector: OR minterms for digits 2,3,5,7.
15) Blank if all higher digits zero; gate leading zeros detector to 7-seg enable.
16) Even/odd = XOR of all bits.
17) Binary→Gray: G3=B3, G2=B3⊕B2, G1=B2⊕B1, G0=B1⊕B0.
18) Gray→Binary: B3=G3, B2=B3⊕G2, B1=B2⊕G1, B0=B1⊕G0.
19) Hazard: asynchronous changes can glitch outputs; fix with registered inputs or synchronizers.
20) Any Boolean realized by programming product terms and OR plane in PLA.

### Arithmetic Circuits (20)
1. Derive sum and carry equations for a full adder.
2. Implement a 4-bit ripple-carry adder and state worst-case delay formula.
3. Design a 4-bit carry-lookahead adder; write generate/propagate equations.
4. Compare RCA vs CLA area-delay trade-offs.
5. Design a 4-bit binary adder-subtractor using XOR and carry-in trick.
6. Build a 4-bit incrementer with minimal logic.
7. Design a BCD adder and explain when to add 6.
8. Show detection logic for BCD overflow in Q7.
9. Create a fast adder using carry-select; choose block size and justify.
10. Implement a Wallace tree for multiplying two 4-bit numbers; count CSA levels.
11. Compare array multiplier vs Booth multiplier conceptually.
12. Implement signed 2's complement addition and overflow detection logic.
13. Design a 4-bit comparator using subtraction and overflow sign bits.
14. Build a barrel shifter for 4-bit word with control signals.
15. Implement restoring division steps for an unsigned 4-bit by 3-bit example.
16. Explain non-restoring division difference from restoring.
17. Design saturating adder for 8-bit signed numbers.
18. Show how to detect carry vs overflow in unsigned vs signed addition.
19. Implement an ALU slice supporting add, subtract, AND, OR, XOR with a 2-bit select.
20. Estimate delay of carry-select adder with blocks of size 2 for 8-bit width.

#### Solutions — Arithmetic Circuits
1) Full adder: S = A ⊕ B ⊕ Cin; Cout = AB + ACin + BCin.
2) RCA = chain of full adders; worst delay ≈ N·(tcarry).
3) CLA: G = AB, P = A ⊕ B; C1=G0+P0Cin, C2=G1+P1G0+P1P0Cin, etc.; S = P ⊕ Ci.
4) RCA small/slow; CLA larger/faster (log depth).
5) Use B ⊕ M and Cin=M to add/subtract.
6) Incrementer: ripple half-adders with Cin=1.
7) BCD adder: add 6 when Cout=1 or S>1001; else keep sum.
8) Detect correction when Cout=1 or (S3·S2) + (S3·S1).
9) Carry-select: precompute with Cin 0/1 per block; mux by incoming carry; block size tradeoff √N.
10) Wallace tree: compress partial products with CSAs; 4-bit × 4-bit needs 2 CSA levels then final adder.
11) Array multiplier regular layout, longer delay; Booth reduces partial products for signed numbers.
12) Overflow (signed) when inputs same sign and result differs; detect via Cout⊕Cprev.
13) Comparator via subtract A−B; use sign/overflow to flag GT/LT/EQ.
14) Barrel shifter: use 2 levels of 2:1 MUXes for shifts 1,2 bits controlled by S1,S0.
15) Restoring divide: shift-subtract loop; example 4-bit/3-bit yields quotient 4 bits, remainder <3.
16) Non-restoring alternates add/sub based on sign of partial remainder; fewer restorations.
17) Saturating adder clamps to 0111... or 1000... on overflow.
18) Unsigned carry-out indicates overflow; signed overflow via sign-bit check (same as Q12).
19) ALU slice: select logic with 2-bit op; arithmetic via adder with operand mux/XOR.
20) 8-bit CSLA with 2-bit blocks: delay ≈ tcarry(2-bit RCA) + mux delay × 3 stages (about 3*(tcarry2 + tmux)).

### Sequential Basics: Flip-Flops, Timing, and Hazards (20)
1. Derive characteristic equations for SR, JK, T, and D flip-flops.
2. Convert JK to D flip-flop using minimal logic.
3. Derive excitation table for JK from present/next states.
4. Explain setup and hold time with timing diagrams.
5. Show metastability risk when violating setup time; describe MTBF qualitatively.
6. Use two-flop synchronizer for async input; draw connection.
7. Compare level-sensitive latch vs edge-triggered flip-flop.
8. Explain clock skew and its impact on race conditions.
9. Compute max clock frequency given Tclk-q = 5 ns, Tcomb = 8 ns, Tsetup = 2 ns, skew = 1 ns.
10. Determine hold time violation for Tclk-q = 1 ns, Tmin path = 0.5 ns, Thold = 0.8 ns, skew = −0.2 ns.
11. Show how to generate T from D and vice versa.
12. Illustrate a gated clock pitfall and propose clock-enable alternative.
13. Explain asynchronous preset and clear; discuss hazards when both asserted.
14. Show racing in level-sensitive latches and how to avoid with master-slave.
15. Explain dynamic hazards and contrast with static hazards.
16. Use Karnaugh maps to find T inputs for a given next-state table.
17. Design edge detector for a pulse using flip-flops.
18. Explain debouncing a mechanical switch with an SR latch or synchronizer.
19. Show a hazard-free two-level implementation for F = A'B + AB'.
20. Discuss glitch risks when mixing asynchronous inputs into combinational logic.

#### Solutions — Sequential Basics
1) SR: Q+ = S + R'Q; JK: Q+ = JQ' + K'Q; T: Q+ = T'Q + TQ'; D: Q+ = D.
2) D = JQ' + K'Q.
3) Excitation: derive JK needed for 00→01 (J=1,K=X), etc.
4) Setup/hold define sampling window around clock edge.
5) Violating setup/hold can metastable; MTBF grows exponentially with slack.
6) Two cascaded DFFs on async input mitigate metastability propagation.
7) Latch is level-sensitive; FF edge-triggered.
8) Positive skew can cause hold issues; negative skew can cause setup issues.
9) Fmax = 1 / (Tclk-q + Tcomb + Tsetup + skew) = 1 / (5+8+2+1) ns ≈ 62.5 MHz.
10) Hold check: Tclk-q + Tmin + skew = 1 + 0.5 − 0.2 = 1.3 ns > Thold 0.8 ⇒ no violation.
11) T from D: T = D ⊕ Q; D from T: D = T ⊕ Q.
12) Gated clocks create skew/glitches; prefer clock-enable gating data path.
13) Async preset/clear override; asserting both can be illegal/metastable.
14) Race in level-sensitive latches when transparency overlaps; fix with master-slave or non-overlap clocks.
15) Dynamic hazards are multiple glitches during transition; static hazards single glitch.
16) Map next-state table to K-map for T inputs: T = Q ⊕ Q+.
17) Edge detector: use delayed version; rising-edge Z = X · Xdel'.
18) Debounce with SR latch or digital filter after synchronizer.
19) Hazard-free two-level for A'B + AB' use XOR implemented as (A+B)(A'+B').
20) Async inputs cause glitches; register/synchronize them before logic.

### Counters, Registers, and FSM Design (20)
1. Design a 4-bit asynchronous ripple counter; show count sequence.
2. Modify Q1 to make a modulo-10 synchronous counter; list terminal state logic.
3. Design a Gray-code counter for 4 bits; give transition list.
4. Implement a Johnson counter for 5 stages; show sequence length.
5. Build a ring counter with one-hot initialization logic.
6. Design a bidirectional up/down counter with enable.
7. Use a loadable synchronous counter to implement a clock divider by 12.
8. Compare ripple vs synchronous counters for speed and skew.
9. Design a 4-bit shift register with serial-in serial-out; show timing.
10. Design serial-in parallel-out register; specify control signals.
11. Implement parallel load and shift register (PISO/PIPO) differences.
12. Create a Moore machine that outputs 1 after seeing three consecutive 1s (overlap allowed).
13. Create a Mealy machine that asserts 1 on pattern 010 (overlap allowed).
14. Draw state reduction steps for equivalent states in an FSM.
15. Encode FSM states using one-hot and binary; compare pros/cons.
16. Add output glitch prevention using registered outputs in a Mealy machine.
17. Design a traffic light controller with minimum states; include timer inputs.
18. Model a vending machine FSM that accepts 5, 10, and 25 units; vend at 30.
19. Show how to detect and recover from unused states using reset logic.
20. Map FSM next-state equations into a PLA or PAL structure.

#### Solutions — Counters, Registers, and FSM Design
1) Ripple counter: cascade T or JK FFs with T=1; counts 0000→1111.
2) Mod-10 sync counter: detect 1010 and clear/load 0000; use JK excitations as in earlier design.
3) 4-bit Gray counter sequence 0000,0001,0011,0010,0110,0111,0101,0100,1100,1101,1111,1110,1010,1011,1001,1000.
4) Johnson (5-stage) length 10 states: shift complemented Q4 into Q0.
5) Ring counter needs one-hot init (e.g., 00001); shift left with wrap.
6) Up/down counter: use XOR of direction with T or with adder (+/-1).
7) Divide-by-12: preset/load counter to 11 and count up with terminal count reload.
8) Ripple slower, skew-prone; synchronous faster, cleaner edges.
9) SISO shift register: chain DFFs, feed serial in, take serial out last stage.
10) SIPO: same chain, tap all stages for parallel outputs.
11) PISO loads parallel via muxed D inputs; PIPO loads/shifts as configured.
12) Moore 3-ones detector: 4 states (0,1,2,3 ones); assert output only in state 3.
13) Mealy 010 detector: 3 states tracking prefix; output on seeing 0-1-0 with overlap.
14) State reduction: identify equivalent rows/columns, merge, redraw transitions.
15) One-hot simpler decoding, more FFs; binary fewer FFs, denser decoding.
16) Register Mealy outputs or add output flip-flop to avoid glitches.
17) Traffic light FSM: states for NS-green, NS-yellow, EW-green, EW-yellow; timers drive transitions.
18) Vending FSM: states by credit (0,5,10,15,20,25,30 vend); add outputs for change if needed.
19) Detect unused states via default branch to reset.
20) Implement next-state/output equations as product terms into OR plane of PLA/PAL.
