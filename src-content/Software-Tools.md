# Software Tools

## Command-Line Arguments (CLAs)

Command-Line Arguments (CLAs) are a very efficient way to modify or
customize the behaviour of a program without the need to change
the actual code itself, and of course not even re-generate it (ie.
recompile it).

CLAs represent a way in which users can provide additional information
to specify how they would like to execute the program. They can customize
actions, modify behavior of the program and even provide data or additional
details to the execution of the program.

At a very high level, one can classify CLAs in two main categories:
   - predefined,
        e.g. flagged arguments -- `--cpu`, `-l`, etc.

   - arbitrary,
        e.g. filenames or values provided.

Somehow, although arbitrary CLAs appear to be more ``generic'' they usually
have constraints associated to them.
For instance, in the case of a filename that indicates a source of data, the
restriction would be that the file exists and the right permissions to access it.
In other cases, other restrictions would also be present related to the type
or nature of the data; e.g. numerical values, or positive/negative, etc.

Similarly, there is a third category/type, named *positional* -- which in reality
indicate that these are usually not flagged but neither arbitrary.
The suppose to be pass to the program in a particular fashion, following an specific
order or position -- hence their name.
And because of this, their positions imply assumptions of what type of information
they provide to the program.

Understanding what actions to take and information is passed to the program by
utilizing CLAs, is usually known as *CLA parsing*.


### CLAs in C:
In C, for enabling the processing and parsing of CLAs we need to recognize that
`int main()` is nothing else that another function -- with some exceptional features,
such as, being the **entry point** of execution.
But other than that, a typical function that we can define in our C programs.
So, nothing will stop us from declaring arguments that the function could receive.
And in particular this is the way in which we will allow to receive the CLAs
from the execution line,


```
int main(int argc, char** argv ) {
    ...

}
```

where `argc` is an integer representing how many arguments have been passed to the
program, and `argv` is an array of strings containing each CLA in each element of the
array.

Notice that `argv[0]` contains the name of the program being executed, and that
all CLAs indicated in this way are represented as strings.


### Defensive Programming
To this very last point, there is a critival relevance between programs
that accept CLAs and the so-called *defensive programming* strategies.
Considering the case of CLAs, these represent ways to check that whatever
the user is inputing is a valid and sensitive choice for the program.
Without these checks the execution, results and integrity of the program
could be easily be compromised.


