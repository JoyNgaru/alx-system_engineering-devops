0x03. Shell, init files, variables and expansions
| `0-alias` | Creates an alias |
		
| `1-hello_you` | Prints `hello user`, where user is the current Linux user |
		
| `2-path` | Add `/action` to the `PATH`. `/action` should be the last directory the shell looks into when looking for a program |
		
| `3-paths` | Counts the number of the directories in the `PATH` |
		
| `4-global_variables` | Lists environment variables |
		
| `5-local_variables` | Lists all local variables and environment variables, and functions |
		
| `6-create_local_variable` | Creates a new local variable named `BETTY` |
		
| `7-create_global_variable` | Creates a new global variable named `HOLBERTON` |
		
| `8-true_knowledge` | Prints the result of the addition of 128 with the value stored in the environment variable `TRUEKNOWLEDGE`, followed by a new line |
		
| `9-divide_and_rule` | Prints the result of `POWER` divided by `DIVIDE`, followed by a new line |
		
| `10-love_exponent_breath` | Displays the result of `BREATH` to the power `LOVE` |
		
| `11-binary_to_decimal` | Converts a number from base 2 to base 10 |
		
| `12-combinations` | Prints all possible combinations of two letters, except `oo` |
		
| `13-print_float` | Prints a number with two decimal places. The number is stored in the environment variable `NUM` |
		
| `14-decimal_to_hexadecimal` | Converts a number from base 10 to base 16 |
		
| `100-rot13` | Encodes and decodes text using the rot13 encryption |
		
| `101-odd` | Prints every other line from the input, starting with the first line |
		
| `102-water_and_str` | Adds the two numbers stored in the environment variables `WATER` and `STIR` and prints the result |

==========
0-alias

#!/bin/bash
alias ls="rm *"

==========
1-hello_you

#!/bin/bash
echo "hello $USER"

==========
2-path

#!/bin/bash
export PATH=$PATH:/action

==========
3-paths

#!/bin/bash
echo $((`echo $PATH | grep -o ":/" | wc -l`+ 1))

==========
4-global_variables

#!/bin/bash
printenv

==========
5-local_variables

#!/bin/bash
set

==========
6-create_local_variable

#!/bin/bash
BEST="School"

==========
7-create_global_variable

#!/bin/bash
echo $(($BEST School))

==========
8-true_knowledge

#!/bin/bash
echo $(($TRUEKNOWLEDGE + 128))

==========
9-divide_and_rule

#!/bin/bash
echo $(($POWER / $DIVIDE))

==========
10-love_exponent_breath

#!/bin/bash
echo $((BREATH**$LOVE))

==========
11-binary_to_decimal

#!/bin/bash
echo $((2#BINARY)o)

==========
12-combinations

#!/bin/bash
echo {a..z}{a..z} | tr " " "\n" | grep -v "oo"

==========
13-print_float

#!/bin/bash
printf "%.2f" $NUM | sort

==========
100-decimal_to_hexadecimal

#!/bin/bash
printf '%x\n' $DECIMAL

==========
101-rot13

#!/bin/bash
tr `echo {a..z} | tr -d ' '` `echo {n..z} $(echo {a..m} | tr -d ' '` | tr `echo {A..Z} | tr -d ' '` `echo {N..Z} $(echo {A..M}) | tr -d ' '`

==========
102-odd

#!/bin/bash
perl -lne 'print if $. % 2 ==1'

==========
103-water_and_stir

#!/bin/bash
echo $(printf %o $(($((5#$(echo $WATER | tr 'water' '01234'))) + $((5#$(echo $STIR | tr 'stir.' '01234'))))) | tr '01234567' 'bestchol')

