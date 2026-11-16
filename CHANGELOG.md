# Changelog

## 1.0.2
Bug fixes found by testing ~470 more real-world VCL files (Magento, Fastly Magento 2 module, FOSHttpCache, Ibexa,
Wikimedia, Varnish Book):
- `return (lookup)` in `vcl_hash` no longer makes a Varnish file count as Fastly VCL (which caused a false error).
- Return actions that older Varnish versions accept are a weak warning instead of an error: `return (miss)` in
  `vcl_hit` (Varnish 4.1–6.1, incl. 6.0 LTS), `return (fetch)` in `vcl_hit` (4.x).
- Fastly snippet files (code without an enclosing `sub`): bare function calls such as `h3.alt_svc();` parse, local
  variables declared in another snippet are not reported, and Fastly-only variables such as `req.url.ext` count
  towards Fastly detection.

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
