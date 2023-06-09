Download Link: https://assignmentchef.com/product/solved-cs240-homework-3-integer-to-quaternary-string
<br>
The decimal number system probably arises from our tendency of counting with our fingers. It is not the only way. A tribe of people have so many four-legged animals that they use the quaternary number system – base 4. The digits are 0, 1, 2, and 3. For example, one, two, three, four, five, six, seven, and eight are represented as 1<sub>4</sub>, 2<sub>4</sub>, 3<sub>4</sub>, 10<sub>4</sub>, 11<sub>4</sub>, 12<sub>4</sub>, 13<sub>4</sub>, and 20<sub>4</sub>. Another tribe love their toes as much as fingers so they use the vigesimal number system – base 20. The digits are 0, 1, <em>…</em>, 9, A, B, <em>…</em>, and J. For example, the decimal numbers 30, 31, and 32 are represented as 1<em>A</em><sub>20</sub>, <em>B</em><sub>20</sub>, and 1<em>C</em><sub>20</sub>.

This assignment is to write C code that converts a <em>positive </em>integer among its quaternary, decimal, and vigesimal representations.

<h2>2            Integer to Quaternary String</h2>

Write the C function itoq() to covert an integer to a quaternary string. Its prototype is described in the header file itox.h. Write your code in the file itox.c. You can build from the template itox.c on BlackBoard.

The idea behind itoq() is to convert an int variable (an int has 32 bits on our machine) directly to an ASCII string of quaternary digits, ’0’, <em>…</em>, ’3’. In this assignment, we will consider only positive integers. The algorithm is as follows.

<ol>

 <li>Divide the int by 4.</li>

 <li>The remainder is the first quaternary digit, to be placed in quaternaryStr[15]. Use ’0’ to represent remainder = 0, ’1’ for remainder = 1, and so on.</li>

 <li>Update the int to be the quotient.</li>

 <li>Repeat steps 1, 2, and 3 for sizeof(int) * 4 times.</li>

</ol>

When Step 2 is executed for the second time, the quaternary digit will go into quaternaryStr[14]; when Step 2 is executed for the third time, the hex digit will go into quaternaryStr[13]; and so on.

<ol start="5">

 <li>Terminate quaternaryStr with ’ ’.</li>

</ol>

Note that the array quaternaryStr declared by the caller can be declared with a size sizeof(int) * 4 + 1. sizeof() is evaluated at compile time to be the number of <em>bytes </em>in a variable of a given type. For example, it is 4 bytes to an int on our machine, but it might be 8 bytes on a different machine. Thus sizeof() allows your code to be portable.

<h2>3            Quaternary String to Integer</h2>

Write the C function qtoi() to convert a quaternary string to an integer. Its prototype is also described in itox.h. Write your code in file itox.c. Your code should only accept the valid quaternary digits: 0, <em>…</em>, 3. An algorithm is as follows.

<ol>

 <li>Start at the last character in the string, which is the least significant digit.Remember to skip over the ’ ’ character.</li>

 <li>Convert the character to its decimal equivalent.For example, character ’2’ is 2.</li>

 <li>Multiply the decimal number by powers of 4.</li>

</ol>

The last character will be multiplied by 4<sup>0</sup>, the next by 4<sup>1</sup>, and so on.

<ol start="4">

 <li>Repeat for all of the characters in the quaternary string.</li>

 <li>Sum the products.</li>

</ol>

<h2>4            Integer to Vigesimal String</h2>

Write similar functions for conversions to and from vigesimal strings. The differences are the following:

<ul>

 <li>The vigesimal number system is base 20.</li>

 <li>The digits are ’0’, <em>…</em>, ’9’, ’A’, <em>…</em>, ’J’.</li>

 <li>From a 32-bit int, there can be at most 8 vigesimal digits. So vigesimalStr[] must have sizeof(int) * 2 + 1 bytes.</li>

</ul>

<h2>5        The Driver</h2>

The driver is the main program that will call itoq(), qtoi(), itov(), and vtoi(). This is not the same thing as a device driver. The driver should be named itoxDriver.c, and you can use the stub itoxDriver.c from BlackBoard.

Now you have three files of source code: the header file itox.h, the utility file itox.c, and the driver itoxDriver.c. The following is how you compile multiple files into one executable, and test your code.

gcc -Wall itox.c itoxDriver.c -o itox

./itox &lt; test.txt

You are not allowed to use any integer to string manipulation library functions, such as itoa(), etc.

Write a readMe.txt file, and discuss what you found difficult about this assignment, how you planned your approach to it, and what you learned completing it.

<strong>Files to email me:</strong>

<ol>

 <li>c</li>

 <li>c</li>

 <li>txt</li>

</ol>