# Bad Habits

In this section we want to present and discuss observed ``bad habits''
that more common than not are found in the CS folklore.


* global variables are evil!
    - break modularity
    - make our codes vulnerable
    - unadvertible source of bugs
    - avoid them at all cost!

* self-document code does not exist!
    - the statement that clean and well written code does not require comments,
    is a fallacy! I promise you, as elegant and simple you may think your code is,
    it will come the time when you come back to your code (maybe a few months or even years later)
    and you will wish you had added comments to it.
    - the comments are a way to explain what the code is doing, but also what we
    believe/suppose it is doing, ie. to explain in plain English what your mental model
    of what the implementation corresponds to.

* comments and documentation are not the same thing!
    - comments describe the implementation details at the level that the programmer needs to know
    and understand it, in order to be able to modify, use it or even rewrite it.
    - documentation, describes the way in which the implementation can be used and the
    intrinsic details needed to understand how things are being done, mostly to validate
    assumptions of how it could and should be used.
    Essentially the documentation describes thigns at the level of an API.

* `print`-statements are not the way to debug!
    - this is not the way to debug, for multiple reasons it can easily backfire on you.
    - there is a proper way to debug and that is to use an specific tool, i.e. a debugger, such as `gdb`.

* modularity is just to create functions!
    - Incorrect!
    - modularity implies to create independent and isolated pieces of software (ie. modules) than perfectly work and be compiled separately.
    - in C, this implies at the minimum to at least creating *header files*.


---

