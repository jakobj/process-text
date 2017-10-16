# process-text

Simplifies processing of plain text files according to certain rules. These rules are defined via a json dict, specifying input files, output files and replacement options.

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
          "<wrong extension>": "<correct extension>"
        }
      }
    }
