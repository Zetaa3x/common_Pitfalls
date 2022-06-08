1) When organizing source files into folders(or moving files in general), don't forget it affects the directory in which the code thinks it's in. 
	e.g	I moved my files into two folders. Source files to "src" and .html template files to "templates"

	Problem: One of my handlers was trying to parse "templates/index.html" but it couldn't cause the templates file is not in the same directory.
	Solution: Change parameter in my ParseFiles() function from "templates/index.html" to ".../templates/index.html"  

	DEBUG: My code worked before I organized it into seperate folders and went to bed. When I came back to work on it, my template wasn't loading at the endpoint I wanted 
	it to. 
	1)First thing I did was comment some stuff out and then see if it worked. Nope. 
	2)Second thing I did was see if other endpoints were working which it did. So it wasn't any issue with the majority of code. 
	3)I finally decided to read the code line by line, processing the flow of logic. My code was the same from when it worked before so why wasn't it working now? 
	4)I googled other people's template handler functions and compared them with mine. They both looked the same so my code should have worked. 
	4)Going back to the template handler, I noticed I was ignoring the error handler so I logged a string to see if it would print out and... Voila! 
		The string was printed out so there 100% is an error with parsing the file. I looked at the html/template documentation to see if the ParseFiles() is a deprecated
		function and it wasn't, so there definitely was something wrong somewhere. 
	5)Playing around with file explorer, I came to realize the files aren't in the same folder anymore and then the solution came to my head. It was a simple fix for a 
		simple problem.   	       
	
	TIME TAKEN: 20-40 mins
