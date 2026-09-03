# Porting notes

**This project's test suite requires Linux.** elfcat parses ELF files, and a large share of
the generated tests use the freshly compiled `./executable` itself as the ELF input fixture.
On macOS the compiled binary is Mach-O, so those tests fail with
`Failed to parse ELF: mismatched magic: not an ELF file` (≈146 of 564 scored tests on
macOS/arm64; the rest pass). On Linux the binary is ELF and the full suite is expected to
pass — gold verification should be completed on a Linux machine before this project is
offered to students, and students should be told to work on it under Linux.

Four branches (d3f472ddbaa3, dccde97f51ad, eb08ed5d950d, f85f34649887) legitimately contain
zero tests — ProgramBench's tests.json records no tests for them.
