# TypeScript
Chai aur TypeScript


# Day 1
The TypeScript Compilation Flow
TypeScript does not execute directly; it must be converted to JavaScript [00:55]. The process involves five main steps:

Lexer (Tokenization) [04:11]

Function: Scans the code and breaks it down into tokens (like const, let, function, return). This process is called tokenization.

Checking: Catches obvious errors like a missing semicolon or an unmatched parenthesis.

Parser [05:13]

Function: Takes the tokens and builds an Abstract Syntax Tree (AST) (also sometimes called a Concrete Syntax Tree) [05:28].

AST: A tree structure that visualizes the entire language and data flow of your code, which is a complex task but essential for understanding the code's structure.

Binder [07:12]

Function: Takes the AST and adds special TypeScript context before checking.

Tasks:

Creates Symbol Tables for additional TypeScript symbols (like type annotations, interfaces, and structs) [07:29].

Sets up Parent Pointers to allow the compiler to navigate up and down the AST [07:54].

Creates Flow Nodes to track control flow logic (like if/else statements) [08:10].

Checker (Type Checker) [09:09]

Function: Performs the strict type checking that TypeScript is known for [10:18]. This is the step that was missing from JavaScript, which is why TypeScript was created [02:53].

Process: It typically makes two passes through the code to perform a deep structural analysis [10:07]. It ensures that the data type of a variable or a symbol is not unexpectedly changed or misused during the code's execution.

Editor Integration: Editors like VS Code can give you errors and warnings because they can access this checker logic [11:00].

Emitter (Generator) [11:24]

Function: Generates the final output files and strips away all TypeScript-specific syntax.

Output: Creates three types of files:

.js (JavaScript): The final executable code [11:38].

.d.ts (Declaration File): Used for type information [03:22].

.js.map (Source Map File): For debugging [03:34].

Stripping: The Emitter removes TypeScript type annotations (e.g., : string) because the final JavaScript code does not understand them [12:03].