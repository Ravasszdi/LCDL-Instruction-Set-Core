# LCDL-Instruction-Set-Core

## Instruction Set
| instruction name | instruction description |
| --- | --- |
| nop       | no op cpu instruction |
| and A B C | `A` and `B` -> `C` |
| or  A B C | `A` or `B` -> `C`  |
| not A B   | not `A` -> `B`  |
| xor A B C | `A` xor `B` -> `C` |
| eql A B C | `A` == `B` -> `C` |
| add A B C | `A` + `B` -> `C` |
| sub A B C | `A` - `B` -> `C` |
| mul A B C | `A` * `B` -> `C` |
| div A B C | `A` / `B` -> `C` |
| mov A B   | move `A` to `B` |
| shr A B   | bit shift `A` to the right by `B` amount | 
| shl A B   | bit shift `A` to the left by `B` amount |
| if A      | if `A` is `TRUE` than it will exacute the next line of code, if `A` is `FALSE` that it skips the next line |
| nif A      | if `A` is `FALSE` than it will exacute the next line of code, if `A` is `TRUE` that it skips the next line |

The outbut **MUST** be a memory address!

## Memory address and literals
| syntax | description |
| --- | ---|
| >b******** | binery literal |
| >d******** | decimal literal |
| >o******** | octo literal |
| >x******** | hexadecimal literal |
| <b******** | binery address |
| <d******** | decimal address |
| <o******** | octo address |
| <x******** | hexadecimal address |

## Registers
| Name | Funciun |
| --- | --- |
| pcs | program stack counter |
| dlt | delta time |
| rtm | run time   *!! need to reassess !!* |
| * | * |

## Formating
The instructions are separetid by `;` new line symbols are ignored.

For exemple:
```
nop;
mov >d42 <x000f;
mov >d69 <x001f;
add <x000f <x001f <x002f;
```
or
```
nop;mov >d42 <x000f;mov >d69 <x001f;add <x000f <x001f <x002f;
```
Both are correct.
