\# Pipeline Tests



This folder contains instruction programs used to verify the pipelined CPU implementation.



---



\## Test Programs



\### full\_instructions\_test



A comprehensive test that verifies correct execution of several instruction types.



The program includes:



\- Arithmetic instructions

\- Register operations

\- Memory instructions

\- Branch instructions



---



\## How to Run



1\. Open `cpu\_pipelined.circ`.

2\. Load the test program into instruction memory.

3\. Run the clock.

4\. Observe register file and memory values.



---



\## Expected Behavior



Registers and memory should match the expected outputs defined in the test program.



Note: since hazard detection is not implemented yet, instructions with data dependencies may not execute correctly.

