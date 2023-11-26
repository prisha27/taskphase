# Play Nice
>In the given python file there is a wikipedia page which shows description about the cipher that is being used i.e. play fair cipher.
>Going through the webpage we understand the way of encryption used for the playfair cipher is:
>if letters are in same row --- then we use the right shifteed letter
>if letters are in same column --- we use the next row same column element.
>if none of the above two mentioned condition satisfies then--- we take the elements and form rectangle and use the horizontal most element for substitution.
>
>Now on downloading the palyfair.py file we see the method of encryption and on seeing the code we understand that positions are incremented by one and to go back to the orignal position that is to decrypt we need to decrement it by "1".
>
>so the code dor decryption is mentioned below:: 
> >PYTHON SCRIPT
```
def decrypt_pair(pair, matrix):
	p1 = get_index(pair[0], matrix)
	p2 = get_index(pair[1], matrix)

	if p1[0] == p2[0]:
		return matrix[p1[0]][(p1[1] - 1)  % SQUARE_SIZE] + matrix[p2[0]][(p2[1] - 1)  % SQUARE_SIZE]
	elif p1[1] == p2[1]:
		return matrix[(p1[0] - 1)  % SQUARE_SIZE][p1[1]] + matrix[(p2[0] - 1)  % SQUARE_SIZE][p2[1]]
	else:
		return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]
```
using this code entering our key value and encrypted text we will get the plain text which when fetch in our terminal will give us the flag.


![Screenshot from 2023-11-26 17-11-41](https://github.com/prisha27/taskphase/assets/123857524/fc6d299b-b17a-4257-980e-ed8510ff3bff)

