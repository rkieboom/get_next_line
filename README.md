get_next_line

A function that reads a single line from a file descriptor.

Features

Handles multiple file descriptor
Handles edge cases such as empty lines and EOF
Designed to work with multiple file descriptor and read the next line of each file descriptor without losing the context of the last read
Usage

This function can be used as a reference or starting point for your own projects that require reading line by line.

Example
```
#include "get_next_line.h"

int main(int argc, char *argv[])
{
    int fd;
    char *line;

    if (argc == 1)
        fd = 0;
    else if (argc == 2)
        fd = open(argv[1], O_RDONLY);
    else
        return (2);
    while (get_next_line(fd, &line) == 1)
    {
        ft_putendl(line);
        free(line);
    }
    if (argc == 2)
        close(fd);
}
```
