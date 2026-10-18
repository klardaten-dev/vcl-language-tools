# Changelog

## 1.0.1
- Reformat Code for VCL files: lines are indented by block depth (using the file's own tabs or spaces), hand-aligned
  continuation lines keep their alignment, long strings `{"..."}` and inline C are left untouched, and trailing
  whitespace is removed. Spacing inside a line is not changed. Commented-out code keeps its shape, `#FASTLY` macro
  lines stay where they are.
- Parser: Varnish triple-quoted strings `"""..."""`, keywords used as names (`backend esi`, `import goto`), no crash
  on extremely deep nesting.
- `var.get()` / `var.set()` from vmod_var are no longer reported as undeclared Fastly local variables.

## 1.0.0
First release: Varnish and Fastly VCL highlighting, dialect detection, completion, navigation/rename across files, 8 inspections with quick fix, quick documentation, structure view and folding.
