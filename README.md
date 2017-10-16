# process-text

Simplifies processing of plain text files according to certain rules. These rules are defined via a config file with a json dictionary, specifying input files, output files and replacement options.

Here is a simple config file, that reads from `<source file>` and writes all lines from the line containing `<substring>` on to `<target file>`, while replacing all occurrences of `<wrong ext>` with `<correct ext>`:

    {
      "<source file>":
      {
        "structure":
        {
          "<substring>": "<target file>"
        },
        "replace":
        {
          "<wrong ext>": "<correct ext>"
        }
      }
    }

If the optional `structure` dictionary is not provided for a file, all content will be written to a file with the same name as the source file, but with "-mod" inserted right before the extension.
It is possible to specify the same file as a target multiple times for one source file (see example), but currently it is not possible to write to the same file from different source files.

For each file it is possible to define substrings that should be replaced, e.g., to turn all `.pdf` extensions into `.eps`.
To simplify the replacement of multiple strings in a single line, one can optionally define the order of replacement (see example).
After all file-specific replacements have been applied, additional globally defined replacements can be performed.

When working with `.tex` files, remember to escape backslashes with a backslash in the config file!
