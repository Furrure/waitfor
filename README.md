Tired of systemd improperly waiting for certain conditions to be met?
Use `waitfor` for all of your conditional waiting needs. 

`waitfor` is a command line tool that blocks until all specified conditions are met.
It uses options to convey conditions and to configure certain options.

Requires: Python 3.4 or higher, patience

## Options:

#### --check-time \<amount\>
Sets the amount of time the program should wait before performing each condition check, applies to all conditions.

#### --and
Sets the condition that should be met for each condition after it. In this case, every condition after it must be true in order for it to exit.

#### --nand
Sets the condition that should be met for each condition after it. In this case, every condition after it must be false in order for it to exit.

#### --directory-available \<path\>
Sets a condition that returns True if the directory specified is a directory or exists.


### Example
`waitfor --directory-available /home/foo --nand --directory-available /home/bar --check-time 20`

Check every 20 seconds to see if /home/foo exists and /home/bar does not exist, exit when these conditions are met.
