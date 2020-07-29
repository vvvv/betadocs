---
uid: ff589b7b-2a76-4cee-a4ca-139db9933828
---

# What are Regular Expressions? 
Regular Expressions are a widely-used method of specifying patterns of text to search for. Special metacharacters allow you to specify, for instance, that a particular string you are looking for occurs at the beginning or end of a line, or contains n recurrences of a certain character. The <span class="node">RegExpr (String)</span> node is highly useful for splitting up strings into individual parts.  

## Tutorial 1 - Decoding Strings 
### Question
The string i receive from another application (for example written in PD) is as follows  
 ID_number value
example  
 id_1 234
 id_3 12

What is the best way to split this string into id an the corresponding value?  

### Answer
Create a <span class="node">RegExpr (String)</span> node. Note that this node has an elaborate help patch - select the node and press <kbd>F1</kbd>.  
Open up Herr Inspektor and enter the following string in the *Regular Expression* configuration input:  
 id_ ( \d+ ) \s ( \d+ )
You will now notice two additional outputs of the node.   
Put your string in the input of the regexpr. for example:  
 id_1 234 id_3 12 
You will notice two spreads at the outputs - the left containing 1 and 3, the right containing 234 and 12.   

The AsValue node will come handy next.  

### But how does it work? 

Where does this cryptic character sequence   
 id_ ( \d+ ) \s ( \d+ )
come from?  
The sequence translates to the following instructions for VVVV: "Go through the whole input. Look for the following combination of things:"  

id_ | the letters i and d and underscore in that order   
--- | ---  
(\d+) | one or more numerical characters. the brackets indicate that these characters will be put into an individual output pin   
--- | ---  
\s | a single space   
--- | ---  
(\d+) | one or more numerical characters. also in a separate pin do this as often as possible and pile up all matches in individual slices.   

All codes are explained in detail in the reference section below.   

## Tutorial 2 - How can I read lines of a text file line by line? 

Use the Inspektor to enter  

 (.*?) \n

in the Regular expression pin of the <span class="node">RegExpr (String)</span> node - you will notice a new output pin. This pin contains all lines of the file as slices.  

The syntax to do that is nearly as short and simple as possible:   
id_ | the letters i and d and underscore in that order   
--- | ---  
(\d+) | one or more numerical characters. the brackets indicate that these characters will be put into an individual output pin   
--- | ---  
\s | a single space   
--- | ---  
(\d+) | one or more numerical characters. also in a separate pin do this as often as possible and pile up all matches in individual slices.  

to split into words use  
 (\S*) \s*
similarly you will get a pin containing all individual words.   

The <span class="node">+ (String Spectral)</span> might help you getting things together again.   

## Tutorial 3: How can I remove characters from a strings
I want to subtract all numbers of each index. For example take this spread (abcd23, xyz12, 34qwertz)  
I want to get (abcd, xyz, qwertz)  

Answer:   
Feed <span class="node">RegExpr (String)</span> with the regular expression  
 (\D*)
This will return all character blocks which are not composed of numbers (this is the meaning of the capital D).  All other characters are ignored and dont make it to the output.  


# RegExpr Reference
The following reference is very much based of the description of the original freeware component by <a href="http://regexpstudio.com/AnSo/Andrey_Sorokin.html" class="extURL" target="_blank">Andrey V. Sorokin</a> but slightly updated for the use of the component within vvvv.   

## How to create output pins
Use round brackets (...) in the regular expressions to define subexpressions. For each subexpression an output pin is created.  

The SliceCount of the output will change according to the number of matches. If there is no match, the output slice count will be zero. Output Pins are numbered based on the left to right order of their opening parenthesis.  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

## Simple matches

Any single character matches itself (unless it is a metacharacter with a special meaning described below). A series of characters matches that series of characters in the target string, so the pattern "bluh" would match "bluh" in the target string. Quite simple. You can cause characters that normally function as metacharacters or escape sequences to be interpreted literally by 'escaping' them by preceding them with a backslash "\", for instance: metacharacter "\>" match beginning of string, but "\\ " match character "\>", "\\" match "\" and so on.  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

## Escape sequences
Characters may be specified using a escape sequences syntax much like that used in C and Perl: "\n matches a newline, "\t a tab, etc. More generally, \xnn, where nn is a string of hexadecimal digits, matches the character whose ASCII value is nn.  

\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

## Character classes
You can specify a character class, by enclosing a list of characters in \[\], which will match any one character from the list. If the first character after the "\[ is "\ , the class matches any character not in the list.  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

Within a list, the "- character is used to specify a range, so that a-z represents all characters between "a and "z, inclusive. If you want "- itself to be a member of a class, put it at the start or end of the list, or escape it with a backslash. If you want '\]' you may place it at the start of list or escape it with a backslash.  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

## White Space
All whitespace in the regexp is ignored. You can use this to break up your regular expression into (slightly) more readable parts. The # character is also treated as a meta character introducing a comment, for example:  

\((abc) # comment 1  

|   # You can use spaces to format regexp´s    

(efg) # comment 2 )  

This also means that if you want real white space or # characters in the pattern that you'll either have to escape them.  

## Line separators
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

"\>" is at the beginning of an input string, and also immediately following any occurrence of \x0D\x0A or \x0A or \x0D. Note that there is no empty line within the sequence \x0D\x0A. "$" is at the end of a input string, and also immediately preceding any occurrence of \x0D\x0A or \x0A or \x0D. Note that there is no empty line within the sequence \x0D\x0A. "." matches any character (also \x0D\x0A and \x0A and \x0D) Note that "\ .\* $" (an empty line pattern) does not match the empty string within the sequence \x0D\x0A, but matches the empty string within the sequence \x0A\x0D.  

## Predefined classes
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

You may use \w, \d and \s within custom character classes.  

The alphanumeric characters include also:  
Š Œ Ž š œ ž Ÿ À Á Â Ã Ä Å Æ Ç È É Ê Ë Ì Í Î Ï Ð Ñ Ò Ó Ô Õ Ö × Ø Ù Ú Û Ü Ý Þ ß à á â ã ä å æ ç è é ê ë ì í î ï ð ñ ò ó ô õ ö ÷ ø ù ú û ü ý þ ÿ  

Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

## Word boundaries
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

A word boundary (\b) is a spot between two characters that has a \w on one side of it and a \W on the other side of it (in either order), counting the imaginary characters off the beginning and end of the string as matching a \W.  

## Iterators & Greediness

Any item of a regular expression may be followed by another type of metacharacters: iterators. Using this metacharacters You can specify number of occurrences of previous character, metacharacter or subexpression.  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

So, digits in curly brackets of the form {n,m}, specify the minimum number of times to match the item n and the maximum m. The form {n} is equivalent to {n,n} and matches exactly n times. The form {n,} matches n or more times. There is no limit to the size of n or m, but large numbers will chew up more memory and slow down r.e. execution. If a curly bracket occurs in any other context, it is treated as a regular character.  

A little explanation about greediness: "Greedy" takes as many as possible; "non-greedy" takes as few as possible. For example, 'b+' and 'b\* ' applied to string 'abbbbc' return 'bbbb', 'b+?' returns 'b', 'b\* ?' returns empty string, 'b{2,3}?' returns 'bb', 'b{2,3}' returns 'bbb'.  

Examples  

\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

### Excourse

Q: Why does non-greedy iterators sometimes work as in greedy mode? For example, the r.e. 'a+?,b+?' applied to string 'aaa,bbb' matches 'aaa,b', but should it not match 'a,b' because of non-greediness of first iterator? A. This is the limitation of used by TRegExpr (and Perl's and many UNIX’s regular expressions) mathematics - r.e. perform only 'simple' search optimization, and do not try to do the best optimization. In some cases it's bad, but in common it's rather advantage then limitation - because of perfomance and predictability reasons. The main rule - r.e. first of all try to match from current place and only if it's completely impossible move forward by one char and try again from that place. So, if You use 'a,b+?' it match 'a,b', but in case of 'a+?,b+?' it's 'not recommended' (due to non-greediness) but possible to match more then one 'a', so TRegExpr do it and at last obtains correct (but non optimum) match. TRegExpr like Perl's or Unix's r.e. doesn't attempt to move forward and check - would it be 'better' match. Moreover, it cannot be compared in terms 'more or less good match' at all.  

## Alternatives

You can specify a series of alternatives for a pattern using "| to separate them, so that fee|fie|foe will match any of "fee, "fie, or "foe in the target string (as would f(e|i|o)e). The first alternative includes everything from the last pattern delimiter ("(, "\[, or the beginning of the pattern) up to the first "|, and the last alternative contains everything from the last "| to the next pattern delimiter. For this reason, it's common practice to include alternatives in parentheses, to minimize confusion about where they start and end. Alternatives are tried from left to right, so the first alternative found for which the entire expression matches, is the one that is chosen. This means that alternatives are not necessarily greedy. For example: when matching foo|foot against "barefoot, only the "foo part will match, as that is the first alternative tried, and it successfully matches the target string. (This might not seem important, but it is important when you are capturing matched text using parentheses.) Also remember that "| is interpreted as a literal within square brackets, so if You write \[fee|fie|foe\] You're really only matching \[feio|\].  

Examples  

foo(bar|foo) matches strings 'foobar' or 'foofoo'.  

## Back references

Metacharacters \1 through \9 are interpreted as back references. \<n> matches previously matched subexpression #<n>. Examples  
\(.* ?)|will return any printable character (i.e. not spaces, newlines, etc)  
--- | ---  
\<a (.* ?) > (.* ?) </a>|will return the content of the <a> tag on the first output, and the text in between on the second output  
--- | ---  
\( foob [0-9]|a+ r ) |will return all words like 'foob0r', 'foob1r' , 'foobar', 'foobaar', 'foobaaar', ... which will appear in the input text.  
--- | ---  
\( [_a-zA-Z\d\-\.]+ @ [_a-zA-Z\d\-]+ (\.[_a-zA-Z\d\-]+)+ ) |will return all email addresses in a text.  

## Perl extensions
(?imsxr-imsxr) You may use the above syntax to set modifiers in the regexp on the fly. Use this at your own risk and consult the original documentation.  

(?#text) A comment, the text is ignored. Note that the node closes the comment as soon as it sees a ")", so there is no way to put a literal ")" in the comment.   




