# <img src=".pics/lexx_headshot_clear.png" width="100px"/> Lexxeous's Python Basic Blocks: <img src=".pics/basic_block.png" width="100"/>

### Summary:

This program takes a Linux executable as an input, and optionally a list of values as manual basic block leader addresses, and disassembles the executable's `.text` section, at an assembly level, into all of its unique, basic logic blocks.

> You can read more about basic blocks from [the Wikipedia page](https://en.wikipedia.org/wiki/Basic_block).

### How to Run:

You can run `basic_blocks.py` manually using:

```bash
python3 basic_blocks.py <executable_path> [space_separated_list_of_values]
```

where `<executable_path>` can also be `` `which <executable_name>` ``.

#### Using Make:

Alternatively, you can take advantage of the `Makefile` by using:

```bash
make <executable_name>
```

which will disassemble all of the basic blocks for an exacutable called `<executable_name>`.

To include a list of manual leaders, use:

```bash
make <executable_name> leaders=<value>\ <value>\ ... \ <value>
```

where the list of values is separated by escaped space characters "`\ `".

> Values in the leaders list represent addresses in the `.text` section of the chosen executable. The values must be within range and may be of formats hexidecimal or decimal integer.

### Output Files:

The output of all basic blocks is to a file called `basic_blocks.txt`.

The .text section and the entire `<explore>` list is outputted to a file called `text_section.txt`.

### Cleaning Up:

Using `make clean` will remove these two output files. They will be recreated upon running the program again.