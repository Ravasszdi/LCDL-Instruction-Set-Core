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
| 0b0101000x | JMP | 5 | It sets/adds to the `PC` |
| 0b110100xx | BRC | 5 | Branch can be taken by specifying the flags |
| 0b00110000 | SHR | 2 | Id does a right bit shift |
| 0b10110000 | CAL | 5 | Jumps to an addres by setting the `PC` and saves the current `PC`+1 to the call stack |
| 0b01110000 | RET | 1 | Returns to the addres that is on the top of the call stack |
| 0b111100xx | | | |
