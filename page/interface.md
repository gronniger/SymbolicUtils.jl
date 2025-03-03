@def title = "SymbolicUtils.jl — Interfacing"
@def hasmath = false
@def hascode = true
<!-- Note: by default hasmath == true and hascode == false. You can change this in
the config file by setting hasmath = false for instance and just setting it to true
where appropriate -->

# Interfacing with SymbolicUtils.jl

<!-- TODO: document TermInterface.jl -->

\tableofcontents <!-- you can use \toc as well -->

This section is for Julia package developers who may want to use the `simplify` and rule rewriting system on their own expression types.

## Defining the interface

SymbolicUtils matchers can match any Julia object that implements an interface to traverse it as a tree. The interface in question, is defined in the [TermInterface.jl](https://github.com/JuliaSymbolics/TermInterface.jl) package. Its purpose is to provide a shared interface between various symbolic programming Julia packages. 

In particular, you should define methods from TermInterface.jl for an expression tree type `T` with symbol types `S` to  work
with SymbolicUtils.jl

You can read the documentation of [TermInterface.jl](https://github.com/JuliaSymbolics/TermInterface.jl) on the [Github repository](https://github.com/JuliaSymbolics/TermInterface.jl).

## SymbolicUtils.jl only methods

#### `promote_symtype(f, arg_symtypes...)`

Returns the appropriate output type of applying `f` on arguments of type `arg_symtypes`.
