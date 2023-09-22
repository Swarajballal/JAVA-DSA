# Type Casting
Type casting is the process of converting one data type to another.

# Implicit Type Casting
short x = 5;
int y = x;
this is an example of implicit type casting. The compiler automatically converts the value of x to an int and assigns it to y.
but if we do vice versa then will be an error because the compiler cannot convert an int to a short.
![img.png](img.png)
# it depends on type implicit type casting or automatic typecasting needs to have same or higher range of same data type.
float and int are not compatible with each other. so we need to do explicit type casting.
check the above image for more details.

# Explicit Type Casting

int y = 10;
short x = (short)y;   // syntax for explicit type casting
System.out.println(x);
There will be no error because we are explicitly converting the value of y to short and assigning it to x.
we can cast to also byte. but there is loss of precision and data because data is truncated.

# For both implicit and explicit type casting we need to have compatible data types.
int cant be converted to string and vice versa.
# vvimp we can explicitly convert int to float and vice versa.
implicity type casting between int and float is possible.
it is possible to convert int to float implicitly because float has higher range than int.
but it is not possible to convert float to int here we have to do explicit type casting.


