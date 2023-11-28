# ASCII_FTW
> 1. Running ``` file ```  command on the file we get that its a 64-bit ELF file.
> 2. After giving the permissions, the file is in executable form and we can run the program.
>
> SHOW US A MESSAGE:
> ```
> The flag starts with 70.
> ```
> Opening the file with Ghidra, we see Symbol Tree from where we can open our "main function".
> 
>![Screenshot 2023-11-28 203027](https://github.com/prisha27/taskphase/assets/123857524/f133096d-13a1-4e3b-a108-bd814f401015)
> ![Screenshot 2023-11-28 203045](https://github.com/prisha27/taskphase/assets/123857524/3cb469b8-d3da-4433-9343-0b00cdcfcab9)

In the main function we can see the starting value of our flag in hex coded with a printf statement.
Now we find oue flag in hex value, converting the HEX values to ASCII we find our flag.
