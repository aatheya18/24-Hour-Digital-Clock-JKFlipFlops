# 24-Hour-Digital-Clock-JKFlipFlops

This project details the design and implementation of a 24-hour digital clock using fundamental digital electronics principles. The circuit was constructed in Logisim, leveraging JK flip-flops as the core building blocks for the counters. This artifact demonstrates a strong understanding of sequential logic, counter design, and display driver circuitry.

# Features
- 24-Hour Timekeeping: The clock accurately tracks and displays time in a 24-hour format, from 00:00:00 to 23:59:59.
- JK Flip-Flop Based Counters: All counting logic is built from individual JK flip-flops, configured as cascaded ripple counters for seconds, minutes, and hours.
- Manual Connections: The circuit was built from the ground up, with all logic gates and component connections manually wired, providing a deeper understanding of circuit topology.
- Custom Reset Logic: Sophisticated combinatorial logic was designed to handle the critical reset conditions, such as:
  - Resetting the seconds counter from 59 to 00.
  - Resetting the minutes counter from 59 to 00.
  - Implementing the full 24-hour cycle reset from 23:59:59 to 00:00:00.
- BCD-to-7 Segment Decoder: A custom Binary-Coded Decimal (BCD) to 7-segment display decoder was constructed manually using logic gates to ensure the correct time is output to the displays.

# Technical Overview
The clock's architecture is divided into three main sections: seconds, minutes, and hours. Each section uses a pair of cascaded counters.
- Seconds Counter: A pair of cascaded BCD counters track the seconds. The first counter (1's digit) resets to 0 after reaching 9, providing a carry-out signal to the second counter. The second counter (10's digit) resets to 0 after reaching 5, providing a carry-out signal to the minutes counter.
- Minutes Counter: Structured identically to the seconds counter, the minutes counters receive a carry-out pulse every 60 seconds.
- Hours Counter: A pair of counters are used for the hours. The 1's digit counts from 0 to 9, while the 10's digit counts from 0 to 2. The critical reset logic is implemented here to trigger when the clock reaches 24:00:00, resetting all counters to 00:00:00.
All counters are driven by a single, synchronized clock pulse to ensure accurate timekeeping. The output from each BCD counter is fed into the custom-built BCD-to-7 segment decoders, which illuminate the correct segments on the 7-segment displays to show the time.

# Skills Demonstrated
This project solidified my understanding of foundational concepts in digital electronics and sequential circuits, including:
- Sequential Logic Design with Flip-Flops
- Digital Counter and Register Design
- Combinatorial Logic and State Machine Implementation
- BCD Encoding and Decoding
- Logic Gate-level Circuit Construction
- Debugging and Simulation using Logisim
