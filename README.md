# Assignment 1 - Fixed Size Integer Datatypes
In this assignment you will create and print several integer data types using the types provided by the `arpa/inet.h` library.  You will also  perform sever bitwise operations and print the results.

The program will be written in C.

## Input
None.  All values in this assignment will be hard-coded.

## Output
Your program should produce the following output (Note: your output may vary
depending on the value used for the `uint8_t` field):

	------------------------ ------------------------ ------------------------
	Hex Value                Signed Value             Unsigned Value          
	------------------------ ------------------------ ------------------------
	     f0f1 f2f3 f4f5 f6f7     -1084818905618843913     17361925168090707703
	               f123 4567               -249346713               4045620583
	                    ffff                       -1                    65535
	                      7b                      123                      123
	
	123 in binary: 01111011 (BASE)
	132 in binary: 10000100 (one's complement of BASE)
	133 in binary: 10000101 (two's complement of BASE (-123))
	 11 in binary: 00001011 (BASE & 0x0F)
	127 in binary: 01111111 (BASE | 0x0F)
	116 in binary: 01110100 (BASE ^ 0x0F)
	216 in binary: 11011000 (BASE << 3)
	 15 in binary: 00001111 (BASE >> 3)


## Implementation
 - Your program will define 4 fields using the unsigned data types provided in the `arpa/inet.h` library:  `uint8_t`, `uint16_t`, `uint32_t` and `uint64_t`.  You will hardcode the assignment of a different value to each field based on the criteria in the Value Table section below.
 - Your program will print the headers shown in the output below and thEn print a row for each of the fields defined above (by passing the appropriate field to its corresponding function on-by-one).
   - After printing those fields, your program will print the result of performing several bitwise operations on your 8 bit field.  The result of each bitwise operation will be passed to the `print_uint8_t_bits()` function to produce the output seen below.  Note that the 2's complement value must be derived using bitwise operations and basic addition...multiplying by -1 is not allowed.
### Functions
Your program MUST include implementations for the functions corresponding to each function prototype listed here:
 - `void print_uint8_t_bytes(uint8_t number)`
   - This function prints a single line of output containing the hex value, signed value and unsigned value of the 8 bit field passed to it. NOTE: all values printed must be in columns that are 24 characters wide, left padded with spaces.
   - **Returns**:  Nothing
   - **Parameters**:
      1. the bit field to be printed

 - `void print_uint16_t_bytes(uint16_t number)`
   - This function prints a single line of output containing the hex value, signed value and unsigned value of the 16 bit field passed to it. NOTE: all values printed must be in columns that are 24 characters wide, left padded with spaces.
   - **Returns**:  Nothing
   - **Parameters**:
      1. the bit field to be printed

 - `void print_uint32_t_bytes(uint32_t number)`
   - This function prints a single line of output containing the hex value, signed value and unsigned value of the 32 bit field passed to it. NOTE: all values printed must be in columns that are 24 characters wide, left padded with spaces.
   - **Returns**:  Nothing
   - **Parameters**:
      1. the bit field to be printed

 - `void print_uint64_t_bytes(uint64_t number)`
   - This function prints a single line of output containing the hex value, signed value and unsigned value of the 64 bit field passed to it. NOTE: all values printed must be in columns that are 24 characters wide, left padded with spaces.
   - **Returns**:  Nothing
   - **Parameters**:
      1. the bit field to be printed

 - `void print_uint8_t_bits(const char * label, uint8_t number)`
   - This function prints the binary representation of the `uint8_t` value passes as the second parameter.  It accomplishes this by iterating from the most significant bit to the least significant bit printing a "1" if the bit is set, and "0" if it is not set.  HINT: you can do this by continually shifting the bit you're interested in printing to the least significant position, masking out the other bits and printing the resulting value (which will either be 1 or 0 as a result of this).  The value passed as the first parameter is printed after the bits and the string "xxx in binary: " is printed before the bits (where "xxx" represents a 3 digit, space padded decimal representation of the number being printed...see sample output).
   - **Returns**:  Nothing
   - **Parameters**:
      1. The label to be printed after the bits
      2. The bit field to be printed


### Value Table

	varaible type	| Value
	----------------+---------------------------------------------------
	uint8_t 	| You must assign this a value using binary
			| notation.  The value must be an 8-bit, odd
			| positive number.
			|
	uint16_t	| You must express this value in decimal noation
			| and it should be set as the highest integer value
			| that can be held in 16 bits.
			|
	uint32_t	| You must hardcode this field to 0xF1234567.
			|
	uint64_t	| You must hardcode this field to 0xF0F1F2F3F4F5F6F7.

