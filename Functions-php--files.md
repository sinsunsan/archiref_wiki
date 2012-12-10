* **fopen**   
Open a file    
http://php.net/manual/en/function.fopen.php   
http://www.homeandlearn.co.uk/php/php10p3.html

Examples :    
https://gist.github.com/4250723

Mode of opening
```
Mode	Meaning
 	r	Use this to read a file only. The pointer is set to the start of the file.
 	r+	Use this to read and write to a file. The pointer is set to the start of the file.
 	w	Use this to write to a file only. It will erase the entire contents of the file you have open. If no file exists with your chosen name, then it will create one for you
 	w+	Same as "w", but used to read and write.
 	a	Use this to write to a file only, and append data to the end of the file. Doesn't erase contents, in other words.
 	a+	Same as "a", but with read access as well.
 	x	Create a file to write only. But gives you a special warning called E_WARNING.
 	x+	Same as x but with read access as well.
 	t	In Windows, a line break is \r\n. The t converts \n line breaks created on other Operating Systems so that they are readable with Windows
 	b	Force PHP to open the file in binary mode.
```