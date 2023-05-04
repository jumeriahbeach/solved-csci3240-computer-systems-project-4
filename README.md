Download Link: https://assignmentchef.com/product/solved-csci3240-computer-systems-project-4
<br>
Write a C program which accepts two integers on the command-line.

The first integer is the number of pthreads that should be created by the original, main thread. The minimum number of threads to create will be 1 and the maximum number of threads to create will be 4. If the command-line arg is 4, then there will be a total of 5 threads running, including the original thread that created the other 4.

We will refer to the value of the second integer as MAXARG below.

BE SURE TO HAVE THIS AS THE FIRST EXECUTABLE LINE IN YOUR PROGRAM:

alarm(60)

The program must be linked with this file on system64:

~rbutler/public/courses/cs/p4test.o

which contains a function named p4test.p4test takes one integer as an argument and returns an integer return code which is &gt;= 0 for valid arguments.

The goal of the program is to evaluate p4test for all integer values between 1 and MAXARG (inclusive), and to find the argument value for p4test that willmaximize the return code. Evaluation of each argument will take several milliseconds, typically in the neighborhood of 0.1 seconds.

The program should get near-linear speedups as the number of threads increases from 1 to 4.

The main thread should wait for all the created threads to terminate.Then, the main thread should print two values:– the argument that produced the highest return code, and– the highest return code

NOTE:Prior to the due date, p4test’s highest return code will be 8888, but after the due date, the highest return code will become some other value and will be produced by a different argument.

TURNIN info:You should submit a tar file of a directory which contains all of therequired files (makefile, C source files, header files, etc).Sample tar command to create a tar file from a dir:tar cvf p4.tar ./p4dir ## do *NOT* use full pathname of the dirAfter un-tarring the project, I will cd to the dir containing it and type:rm -rf p4rm -f *.omakeIt should build an executable named p4.Then I will test it by typing commands similar to this:./p4 4 100