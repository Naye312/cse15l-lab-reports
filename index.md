## Lab Report 1
### cd commands
1. cd without argument
	* ![Image](Ex1.PNG)
	* Absolute Path: /c/users/Naye
	* Output Explanation: The reason that the directory changes to /h is because the home directory is what the CD command will default to if given no arguments  
	* Error: None, working as intended. 
2. cd with path to directory as argument
	* ![Image](Ex2.PNG)
	* Absolute Path: /c/users/Naye
	* Output Explanation: The reason that the directory changes to /c/users/Naye/lecture1 is because we started from the absolute path and moved to the lecture1 directory when given lecture 1 as an argument.
 	* Error: None, working as intended.
3. cd with path to file as argument
	* ![Image](Ex3.PNG)
	* Absolute Path: /c/users/Naye/lecture1
	* Output Explanation: Nothing happens because the file HelloWorld.java is not a directory and thus the CD command can't do anything with it. 
	* Error: Yes, the error occurs because the file path is not a directory.

### ls commands
4. ls without argument 
	* ![Image](Ex4.PNG)
	* Absolute Path: /c/users/Naye
	* Output Explanation: ls command lists everything in the directory. Since the absolute path is /c/users/Naye, the ls command will list everything there, including the directory lecture1.
	* Error: None, working as intended. 
5. ls with path to directory as argument
	* ![Image](Ex6.PNG)
	* Absolute Path: /c/users/Naye/lecture1
	* Output Explanation: ls command lists every file in the lecture1 directory.
	* Error: None, working as intended. 
6. ls with path to file as argument
	* ![Image](Ex5.PNG)
	* Absolute Path: /c/users/Naye/lecture1
	* Output Explanation: ls command lists every file in the lecture1 directory.
	* Error: None, working as intended.

### cat commands
7. cat without argument 
	* ![Image](Ex7.PNG)
	* Absolute Path: /c/users/Naye/lecture1
	* Output Explanation: Nothing happens because the file HelloWorld.java is not a directory and thus the CD command can't do anything with it. 
	* Error: Yes, the error occurs because the file path is not a directory.
8. cat with path to directory as argument
	* ![Image](Ex8.PNG)
	* Absolute Path: /c/users/Naye/lecture1
	* Output Explanation: Nothing happens because the file HelloWorld.java is not a directory and thus the CD command can't do anything with it. 
	* Error: Yes, the error occurs because the file path is not a directory. 
9. cat with path to file as argument 
	* ![Image](Ex9.PNG)
	* Absolute Path: /c/users/Naye/lecture1
	* Output Explanation: Nothing happens because the file HelloWorld.java is not a directory and thus the CD command can't do anything with it. 
	* Error: Yes, the error occurs because the file path is not a directory. 
