Mini C++ Compiler for If-Else and For Loops
This project implements a mini compiler for C++ subsets, targeting intermediate code generation for conditional statements (if-else), loops (for), and ternary operators. It produces optimized three-address code (TAC) via the following pipeline:

Symbol table generation with expression evaluation.

Abstract Syntax Tree (AST) construction.

TAC and quadruple generation.

Code optimization.

Tools: LEX for lexical analysis and tokenization; YACC for parsing, AST generation, and initial intermediate code; Python for optimization.

Symbol Table Creation
The symbol table supports error detection (undeclared/redeclared variables, missing semicolons) and expression evaluation during semantic analysis.

Intermediate Code Generation
The generator processes an annotated AST from the semantic analyzer, converting it to machine-independent TAC in linear form, represented as quadruples.

Code Optimization
Optimization uses a key-value map (mirroring the symbol table) for variable tracking and value propagation. Techniques include constant folding, constant propagation in sequential blocks, and dead code elimination.

Error Handling
Syntax validation leverages the AST for structural representation, enabling decoupled parsing and validation. Grammar utilizes %left/%right associativity for precedence. AST inspection isolates syntax errors during parsing, separating them from interpretation logic for targeted debugging.
