# VHDL Counter Type Conversion Bug
This repository demonstrates a common but subtle bug in VHDL related to implicit type conversion between integers and std_logic_vector when using integers as output ports.  The issue arises when the counter's value exceeds the range defined for the output port.  The incorrect code doesn't explicitly handle this, leading to unpredictable behavior.

## Bug Description
The provided VHDL code implements a simple counter.  However, the `count` output port is declared as an integer but the implicit type conversion to a suitable std_logic_vector for driving external outputs isn't handled correctly when the count value might exceed the declared range. This might lead to silent truncation or other undesired side effects.

## Solution
The solution demonstrates explicit type conversion and range checking for robust behavior.  By using a `std_logic_vector` type for the output, any issues with implicit conversion between integer and std_logic_vector are eliminated.  Additional error handling can also be implemented for more robust behavior.
