
## File Input/Ouput Operations (IOPs)
Now that we have a more "low level" view of what a file is for the OS and FS, we should clarify that accessing --i.e. reading and writing data from/to files-- is just not one single operation.
Usually this process involves multiple operations, actions and manipulations coordinate by and with the OS.

### Basic I/O opearations
   - Finding a file (`ls`)
     - Check if that file exists, read metadata (file size, date stamp etc.)
   - Opening a file:
      Check if that file exists, see if opening the file is allowed, possibly create it, find the block that has the (first part of) the file system.
   - Reading a file
       Position to the right spot, read a block, take out right part
   - Writing to a file:
      Check where there is space, position to that spot, write the block. Repeated if the data read/written spans multiple blocks.
   - Move the file pointer (*seek*):
      File system must check were on disk the data is.
   - Close the file.


### Basic File I/O Functions (`stdio.h`)

```C
// Open
FILE *fopen(const char *path, const char *mode);


// Close
int fclose(FILE *stream);
```

### Text/ASCII I/O
```C
// Input:
int fscanf(FILE *stream, const char *format,...);
char *fgets(char *s, int size, FILE *stream);
char fgetc(FILE *stream);

// Output:
int fprintf(FILE *stream, const char *format,...);
int fputs(const char *str, FILE *stream);

// Position cursor:
int fseek(FILE *stream, long int offset, int whence);
void rewind(FILE *stream);
```

### Binary I/O
```C
// reading (input)
size_t fread(void *ptr, size_t size, size_t nmemb, FILE *stream);

// writing (output)
size_r fwrite(const void *ptr, size_t size, FILE *stream);
```


## I/O Performance
Any IOP is always going to be the slowest part of any code.
The reason of why this is the case is simple: IOPs mostly involve interactions with hardware which in its main form is constituted by mechanical parts, e.g. HDD.
Hence any mechanical interaction is always going to be substanatially slower than any electronic interactions.
In addition to that, there is the fact that if we are "forcing" a type conversion, e.g. if we are trying to save data (which is usually stored as binary) in memory as "text/ASCII" represented data, then there is a explicit conversion that must be done, involving further cycles of the CPU fully dedicate to these conversions.

