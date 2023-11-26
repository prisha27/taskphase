# File Types
>From this hint : " Remember that some file types can contain and nest other files " we get a hint that there is something to do with the file type.
>On opening the file in the terminal with command "file Flag.pdf " it shows us this message :
>```
>Flag.pdf: shell archive text
>
Now changing permission and running the file again :
![Screenshot from 2023-11-26 19-27-51](https://github.com/prisha27/taskphase/assets/123857524/629e9b05-88af-4737-ac32-9937ac7e4f9d)

Again opening the file :
```
file flag
flag: current ar archive
```
-- It is recognized as a current format ar archive, on extracting from archives using binwalk.
```
binwalk -e flag

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
100           0x64            bzip2 compressed data, block size = 900k
```
it extracts the identified files or data structures.

On extracting details we find out a series of compression is performed :
```
1st : lzip --- lzip -d -k flag
2nd : lz4  --- lz4 -d flag.out flag2.lz4
3rd : lzma --- lzma -d -k flag2.lzma
4th : lzop --- lzop -d -k flag2.lzop -o flag3
5th : lzip --- lzip -d -k flag3
6th :  xz  --- xz -d -k flag4.xz
7th : file flag4
```
Finally shows the ASCII TEXT. on seeing we understand that is in hexadecimal form, using cyberchef tool we can decrypt it and find out the flag.

```
text --> 7069636f4354467b66316c656e406d335f6d406e3170756c407431306e5f
6630725f3062326375723137795f39353063346665657d0a
flag --> picoCTF{f1len@m3_m@n1pul@t10n_f0r_0b2cur17y_950c4fee}





