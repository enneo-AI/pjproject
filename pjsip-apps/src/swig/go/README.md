# pjsua2 Go bindings

The SWIG interface enneo's ACD generates its pjsua2 Go bindings
(`pkg/pjsua2_bindings`) from:

- `pjsua2.i`, the interface;
- `symbols.i`, the symbol list it was generated against;
- `constants.i`, pjsua defines exposed as constants, included from `symbols.i`;
- `../and_string.i`, shared with the other languages.

SWIG's Go module suffixes every generated symbol with a hash of `pjsua2.i`'s
contents, so a change there renames every symbol in the generated code. Add
declarations to `constants.i` instead.

ACD generates the bindings with SWIG 4.4.1 against this tree's headers, in the
`pjsua2-bindings` stage of its Dockerfile.
