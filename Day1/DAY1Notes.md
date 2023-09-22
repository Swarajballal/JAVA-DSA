System.out.println("Hello World");    // is used to print the output on the screen.
sysout + ctrl + space to autocomplete

here system is a class ,out is a subclass or field and println is a method of out class.

# Variables and Data Types
# primitive data types: int, float, double, char, boolean

max value that can be stored in int is 2^31-1 or 2147483647
min value that can be stored in int is -2^31 or -2147483648
short is 2 bytes can bw used to store small numbers(int) max value 32767
short min value -32768
long is 8 bytes max value 2^63-1 or 9223372036854775807L 
here L is needed to tell compiler that it is a long value
minimum value -2^63 or -9223372036854775808L
byte is 1 byte max value 127
min value -128

Floating point data types: float, double

float is 4 bytes or 32 bit memory max value 3.4028235E38
double is floating point number with double precision 8 bytes or 64 bit memory max value 1.7976931348623157E308
precison in float is 8 digits after decimal point and in double it is 16 digits after decimal point.
# vvimp try to use double as it is more precise and makes process faster.

# Literals
Use to explicitly define the value of a variable.
for example float value = 3.14f;
double value = 3.14d;
f,d here are literals

# Char and Boolean
Unlike c and c++ in boolean in java it does not understand 0 as false and 1 as true.
java follows Unicode character set. you can use unicode characters in java as value to char variable.

# Big Decimal 
BigDecimal d1 = new BigDecimal(1.05);
BigDecimal d2 = new BigDecimal(2.55);
System.out.println(d1.add(d2)); // 3.59
instead use string then rounding up will be disabled. and we will get 3.6
big decimal is used for high precision calculations.
so big decimal can solve the issue of rounding up in java.

# Strings
String is a sequence of characters.

# How to declare a string

String name = new String("Swaraj");

'+' Operator is a overloaded operator in java. it can concatenate two strings and can add two numbers.
if one of the operand is string then it will convert the other as a string and concatenate the other operand to the string.
for example:
String var1 = "20";
int var2 = 10;
System.out.println(var1+var2); // 2010

here typecasting takes place. var2 is converted to string and then concatenated to var1.
Typecasting is the process of converting one data type to another data type.

String is a class in java. it is not a primitive data type. there are many methods in string class.
