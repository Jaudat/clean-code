# Chapter 1: Your First C++ Program

## Compiler
	IN VIDEO: Creating your first C++ Program
The C++ compiler used in this course are called two phase compilers. They uses two passes and many intermediate representations to compile your program. Phase 1 is the compiling while the second phase is linking. In the first phase each .cpp file is translated to an .o file (or object file), so for example a main.cpp is translated to main.o. The .o files are the files translated into their binary representation but haven't been linked together so, in the second phase these files are compiled and linked together based on hooks. These hooks are generally statements that are exported or defined elsewhere but are called in the code. At the end of this phase another file is created without the .o extension so for example the main.o may be changed to main

	IN VIDEO: Compiling and Running your Program
To compile the code using GCC, we use the following format:

`[command executable] [output filename (optional)] [input sourcecode] [standards compliance level (optional)]`

for example:
* `[command executable]` = g++
* `[output filename]` = -o hello
* `[input sourcecode]` = main.cpp
* `[standards compliance level]` = -std=c++11

Here are some example commands: 
* `g++ main.cpp`
* `g++ -o hello main.cpp -std=c++11`
* `g++ -Wall -Wextra -Werror -c main.cpp -o hello -std=c++11`

<!-- -->

	IN VIDEO: Introduction to main function in C++
We can only have one main function in a program. It is where the program starts and eventually terminates at. It cannot be overridden. According to the standards we return 0 if it has terminated correctly or a non-zero integer in case of error. If we do not return anything explicitly then the function will return 0 by default. Eitherway the function can only return an int (not std::exit for example). Every program MUST have a global main function.

There are only two formats that the main function can be written as:
* Basic format: `int main() { }`
* Extended format: `int main(int argc, char* argv[]) { }`, Where argv is an array of parameters with argv[0] as the name of the application or an empty string. While argc is a non-negative integer or 0 representing the total number of paramerters to the function.

	IN VIDEO: Dealing with Program Arguments
There conventions for using short and long arguments, with short arguments you use a space as a sperator while with long arguments you use an equal sign. Here is what they would look like and what it would look inside the main function:
* Short Arguments:
	`proc_exec -a hello`
	** argc: 3
	** argv[0]: `proc_exec`
	** argv[1]: `-a`
	** argv[2]: `hello`

* Long Arguments: 
	`proc_exec --action=hello`
	** argc: 2
	** argv[0]: `proc_exec`
	** argv[1]: `--action=hello`

We can always mix and match between short and long form of the arguments

	IN VIDEO:

