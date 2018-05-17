Remarks
=======

This entry graphically displays a simulation of sand falling.
It uses SDL to draw the interface.

The code makes the following assumptions about the underlying system:

* SDL 2 is installed from https://libsdl.org
* "double" is an IEEE 754 floating-point type and sizeof(double)==8
* The compiler supports the C99 standard

In order to simulate the motion of the sand, a cellular automaton is used. The
state transition table is not stored directly. Instead, the program stores the
coefficients of a polynomial that map each state to the correct one. These
coefficients are stored as raw hexadecimal in the V[] array, and they are
reinterpreted as doubles when used. This allows more numeric precision in fewer
characters (base 16 > base 10), and makes the purpose of the array less clear.

The code is laid out graphically as a bucket pouring sand, and it is far easier
to observe this high-level layout than the code's actual function.

The preprocessor is used to both obfuscate the code as a whole and abbreviate
the calls to SDL. Additionally, throughout the code, the variables were named
so that they are short and easily confused with each other.
