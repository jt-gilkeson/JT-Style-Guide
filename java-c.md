# Knicknak's Java/C#/C++ Style Guide

## Spacing 

* Keywords/Conditional Statement always have a space between the keyword and the condition: <code>if (expr), for (int x...)</code>
* Methods names are immediately followed by the opening parentheses: <code>method(), add(x)</code> 
* Operators have a space on each side: <code>x + y, (x == z)</code>
* Exception: No spaces for Increment/Decrement operators: <code>x++</code>
* Semicolons in a for statement are followed by a space: <code>for (int x = 1; x < z; x++) </code>
* Commas separating parameters are followed by a space: <code>method(x, y, z); </code>
* If a brace appears on a line with other text, there should be a space separating the brace from the text: <code>catch {}</code>

Example:
```C#
if ((x + y) == z) 
{
    method();
} 
else if (expr) 
{
    for (int x = 1; x < z; x++) 
    {
         myMethod(x, y);
    }
} 
else 
{
    do 
    {
      	add(z);
    } 
    while (z < y)
}

void myMethod(int x, int y) {}
```

## Braces / Indentation 
All curly braces should be done in the Allman/BSD/C/Braces Left style:
* All Braces should be on their own line
* Opening and Closing Braces should line up vertically
* Pairs of related keywords should line up vertically (if, else if, else) (try, catch, finally) (do, while)
* Conditionals/Loops with only one statement should put braces around that statement
* Exception: Empty methods or catch blocks can have opening and closing braces on the same line as the method declaration: <code>void myMethod() {}</code>

Example:
```C#
try
{
    if (expr)
    {
        statement;
        statement;
    }
    else if (expr)
    {
        statement;
    }
    else
    {
        statement;
        statement;
    }

    do
    {
        statement;
        statement;
    }
    while (x == y)
}
catch (exception e) 
{
    statement;
}
finally
{
    statement;
    statement;
}
```

## Additional Suggestions 
Line up variables and constants:
```C#
private static final int    EXT_COL		= 0;
private static final int    NAME_COL		= 1;
private static final String DISP_NAME_SEPERATOR = " - ";
```

Try to have only 80-120 columns per line.  
If you must break a single statement into multiple lines, try to maximize readability:
```C#
LONG lRet = RegOpenKeyEx(HKEY_LOCAL_MACHINE,
			 "SOFTWARE\\Vertical Networks\\InstantOffice", 
			 0, KEY_READ, &hKeyRoot);
```

For SQL statements, break up lines by keywords:
```C#
csSQL.Format("UPDATE Sysport "
	     "SET Enabled = TRUE, "
	     " StreamChan = (? + VAL(RIGHT(Extension, 6))) "
	     "WHERE Extension BETWEEN ? AND ?");
```

## References 
http://www.tuxedo.org/~esr/jargon/html/entry/indent-style.html

http://jalopy.sourceforge.net/braces.html

http://www.cs.bris.ac.uk/~nathan/programming/looney.html

http://httpd.apache.org/dev/styleguide.html

http://geosoft.no/javastyle.html

http://www.javaranch.com/style.jsp
