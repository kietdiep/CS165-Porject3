# CS165-Porject3

## Part 1 : uid_1022_crack
For part 1 we first found the end of the buffer by printing 'A's untill we seg-faulted. After finding the right amount of 'A's we then found the address for log_result() by using the disassemble command so we could find the stack ebp and overwrite the return address. After we found those locations we passed in the hex address of log_result() to create the file uid_1022_crack.

## Part 2 : uid_1022_crack_advanced
For part 2 we followed a similar process. We first started by finding the address for log_result_advanced() by disassembling the function. We then look for the first function that shows up after. We do this to find how much of padding we need for the call function since we still want to run the call function. After we find the buffer we then overwrite the old return address. After the buffer we added the needed payload for log_result_function().  

## Part 3 : uid_1022_crack_super
For part 3 we started by overwrite the saved return address with the given hex code (0x08048e85). We then had to find the address for the string that we wanted to input. To do this we ran the code and we broke before the call so we could find the corresponding esp so we could change it's pointer. once we found that pointer we added the second input since we still had to pass that into the call function. An important note for this part was that we couldn't buffer with /x00 since that would be considered a null character so we had to imput /x01 instead. After we found the esp and the string pointer we then were able to add the string to the end of our print line. The last step was after we found our esp pointer we needed to change it until it fit with the internal server until we were able to get the right string name.
