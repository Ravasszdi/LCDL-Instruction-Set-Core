# LCDL-Instruction-Set-Core

Based on: [video series](https://www.youtube.com/playlist?list=PL5LiOvrbVo8nPTtdXAdSmDWzu85zzdgRT)

## Instruction Set
| binary representation | instruction name | instruction size (byte) | instruction description |
| --- | :---: | :---: | --- |
| 0b00000000 | NOP | 1 | It does nothin for 1 cycle |
| 0b10000000 | HLT | 1 | It stops the CPU |
| 0b01000000 | LDI | 6 | Loads a literal into a register |
| 0b1100000x | LDM | 4 | Loads a value from/to memory |
| 0b00100000 | NOT | 3 | It does bit wise `NOT` operacion |
| 0b10100000 | AND | 4 | It does bit wise `AND` operacion |
| 0b01100000 | OR  | 4 | It does bit wise `OR` operacion |
| 0b11100000 | XOR | 4 | It does bit wise `XOR` operacion |
| 0b00010000 | ADD | 4 | It adds 2 registers together |
| 0b10010000 | ADI | 6 | It adds a literal to a register immediately |
| 0b01010000 | JMP | 5 | It sets the `PC` |
| 0b110100xx | BRC | 5 | Branch can be taken by specifying the flags |
| 0b00110000 | SHR | 2 | Id does a right bit shift |
| 0b10110000 | CAL | 5 | Jumps to an addres by setting the `PC` and saves the current `PC`+1 to the call stack |
| 0b01110000 | RET | 1 | Returns to the addres that is on the top of the call stack |
| 0b111100xx | | | |

| name | shortened form |
| --- | --- |
| program counret | PC |
| ... | ... |

> ### NOP -> ()
> No operacion.

> ### HLT -> ()
> Ends the prosses.

> ### LDI int32 -> %x
> Loads an Int into a register.
> Format:
>
> `LDI %1 0d42` -> `10000000 00000001 00...101010`

> ### LDM 0xXXXX -> %x
> It loads a value from memory to a register.
> Format:
>
> `LDM %1 0x0001` -> `11000000 00000001 00...001`

> ### STM %x -> 0xXXXX
> It stores a register's value in a memory cell.
> Format:
>
> `STM %1 0x0000` -> `11000001 00000001 00...00`

> ### NOT %x -> %x
> It does bit wise not operacion on the first register and puts the result in the second register.
> Format:
>
> `NOT %1 %2` -> `00100000 000000001 000000010`

> ### AND|OR|XOR %x %x -> %x
> It does bit wise and|or|xor operacion on the first address and second register and puts the result in the third register.
>
> `AND %1 %2 %3` -> `10100000 00000001 00000010 00000011`
>
> `OR  %1 %2 %3` -> `01100000 00000001 00000010 00000011`
>
> `XOR %1 %2 %3` -> `11100000 00000001 00000010 00000011`

> ### ADD %x %x -> %x
> It adds the first register and second register togedher and puts the result in the third register.
>
> `ADD %1 %2 %3` -> `00010000 00000001 00000010 00000011`

> ### ADI %x1 0xXXXXXXXX -> %x1
> It add a number immediately to a register and puts the result back to the original register.
>
> `ADI %1 0d1` -> `10010000 00000001 00...001`

> ### JMP 0xXXXXXXXX -> ()
> It sets the program countert
>
> `JMP 0d10` -> `01010000 00...01010`

> ### BRC NOTZERO|ZERO|NOTCARRY|CARRY 0xXXXXXXXX -> ()
> it performs a `JMP` if the flag condicions are correct
> | Flags | Binary Representation | Descripcion |
> | --- | --- | --- |
> | NOTZERO | 00 | if the previous instructions resoult is not zero |
> | ZERO | 01 | if the previous instructions resoult is zero |
> | NOTCARRY | 10 | if the previous instructions resoult have no carry bit |
> | CARRY | 11 | if the previous instructions resoult have a carry bit |
>
> `BRC NOTZERO 0d10` -> `11010000 00...01010`
>
> `BRC ZERO 0d10` -> `11010001 00...01010`
>
> `BRC NOTCARRY 0d10` -> `11010010 00...01010`
>
> `BRC CARRY 0d10` -> `11010011 00...01010`

> ### CAL 0xXXXXXXXX -> ()
> It sets the program counter but before jumping it stores the current program counter value +1 it the call stack.
>
> ` CAL 0d10` -> `10110000 00...01010`

> ### RET -> ()
> It returs to the adress found at the top of the call stack.
>
> `RET` -> `01110000`
