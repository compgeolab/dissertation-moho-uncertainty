# Create supplementary material

Along with the dissertation, students must submit supplementary material:

* A research diary with a log of their activities
* A zip archive with everything they produced (code, data, etc)

The diary can be produced from the `git log` of this repository (filtered to
only show contributions from the student) and the archive is a zip of the
entire repository. The `Makefile` automates the creation of both of these.

To generate the diary:

1. Edit the `AUTHOR` variable in the `Makefile` to reflect your own name. It
   **must** be the same name you configured git to use. **Only do this once**
   and commit your changes.
1. Run `make diary`. A PDF of the log will be generated automatically in
   `output/diary.pdf`.

To generate the archive:

1. Run `make archive`. A zip of this entire repository will be placed in
   `output/dissertation-archive.zip`. This reflects the `main` branch and won't
   include any uncommitted changes you may have (so `git commit` first).

You can also run `make all` to generate all supplementary material.
