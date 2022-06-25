# REGEX (Regular Expression)


Regex is short for regular expression. Regex is a string of text that allows you to create patterns that hellp match, locate, and manage text. The command line and text editors can find text within a file using Regex. If you work with text or parse large amounts of data Regex can save you time. 

## Summary

Regex (Regular Expression) email. 
```
Matching an Email: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Caret ^ - the beginning of a string
() captures a group
$ - end of string or line
[] character set
a-z matches a character between a-z
0-9 matches a character between 0-9
underscore = underscore
. is an escape character
= - dash = dash
+ means match one or more

```




## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)



## Regex Components

### Anchors
Anchors are  different from literal character, character classes and the dot which match a single character. Anchors do no match any character. They match the position before, after or between characters. The anchor can be used to a certain position. The caret^ matches the position before the first character in the string. By placing a ^a to abc matches a. The letter b cannot be matched because it is second in the string. The dollar sign$ matches after the last character in the string. In this case of abc the c$ matches.  
[reference](https://www.regular-expressions.info/anchors.html)

### Quantifiers
Quantifiers are used to quantify how many times a part of your regex should be repeated. A individual character, a character class or a sub-expression is used to write a quantifier after it so it can be repeated many times. The most common quantifiers: ?, *, +, {N}, {,N}, {N,}, {N,M}. Range Quantifiers {N,M}, The 'N' is a positive integer and 'M' is a positive integer or left blank to represent 'infinity'. The question mark ?, astrik *, and the plus sign + are syntax sugar. The question mark means zero or one, example {0,1}...../colou?r/ will match both color and colour. The astrik * means zero or more, example {0,}. The plus sign + means one or more times, example {1,}.....\d+ search for numbers.
```
Greedy quantifier	Lazy quantifier 	    Description
        *	            *?      	    Match zero or more times.
        +	            +?      	    Match one or more times.
        ?	            ??	            Match zero or one time.
        { n }	        { n }?      	Match exactly n times.
        { n ,}	        { n ,}?	        Match at least n times.
        { n , m }	    { n , m }?	    Match from n to m times.
```        

[reference 1](https://www.javascripttutorial.net/regular-expression-quantifiers/)

[reference 2](https://blog.robertelder.org/regular-expression-quantifiers/)

### Grouping Constructs
Grouping constructs create a sub-expression by placing an expression inside matching open and close paretheses. Quantifiers can be applied to sub-expressions. Each set of parentheses creas a capture number tha is used to identify capturing groups, ranging from 1 - 9(\1 to \9). Capturing groups can be referenced later by their capture number in the regular expression or the replacement string REGEXP_REPLACE. 
[reference](https://www.yellowbrick.com/docs/5.2/ybd_sqlref/regex_capturing_noncapturing_groups.html)


### Bracket Expressions
Bracket Expression is a list of characters enclosed by []. It matches any character listed between the opening and the closing square brackers. The range expression consists of two characters seperated by a hyphen. It matches nay single character that sorts between the characters.To include one of the characters ‘\’, ‘]’, ‘-’, or ‘^’ in a bracket expression, put a ‘\’ in front of it. For example: [d\]]

[reference](https://www.gnu.org/software/gawk/manual/html_node/Bracket-Expressions.html)

### Character Classes
Character classes are a feature introduced in the POSIX standard. It has a special notation for describing list of characters that have a specific attribute. They can vary from country to country.
Character classes is only valid in a regex inside the brackets of a bracket expression. Character classes consist of [:'a keyword denoting the class, and ':]
```  Class	        Meaning
[:alnum:]	Alphanumeric characters
[:alpha:]	Alphabetic characters
[:blank:]	Space and TAB characters
[:cntrl:]	Control characters
[:digit:]	Numeric characters
[:graph:]	Characters that are both printable and visible (a space is
            printable but not visible, whereas an ‘a’ is both)
[:lower:]	Lowercase alphabetic characters
[:print:]	Printable characters (characters that are not control 
            characters)
[:punct:]	Punctuation characters (characters that are not letters, 
            digits, control characters, or space characters)
[:space:]	Space characters (these are: space, TAB, newline, carriage 
            return, formfeed and vertical tab)
[:upper:]	Uppercase alphabetic characters
[:xdigit:]	Characters that are hexadecimal digits
```

[reference](https://www.gnu.org/software/gawk/manual/html_node/Bracket-Expressions.html)

### The OR Operator
Alternation is the term in regular expression that is actually a simple "OR". A verticle line character is used in regular expression. It is used by placing the alternation character between two possible expression(a|b). Alternation can be global across the entire expression, or local when enclosed in the parentheses. For example, the following expression will match either abc or 123:   /abc|123/

[reference 1](https://javascript.info/regexp-alternation)

[reference 2](https://regexland.com/regex-alternation/)

### Flags
A flag is an optionsl parameter to a regex that modifies its behavior of searching. It changes the default searching behavior of a regular expression. It makes a regex search in a different way. Single lowercase alphabetic character is used. For an expression created literally, i.e. using the forward slashes //, flags comes after the second slash. In general notation we can expression this as follows:
/pattern/flags
```

Flag	Name	            Modification
 i	  Ignore Casing	    Makes the expression search case-insensitively.
 g	  Global	        Makes the expression search for all occurrences.
 s	  Dot All	        Makes the wild character . match newlines as
                        well.
 m	  Multiline	        Makes the boundary characters ^ and $ match the
                        beginning and ending of every single line 
                        instead of the beginning and ending of the 
                        whole string.
 y	  Sticky	        Makes the expression start its searching from 
                        the index indicated in its lastIndex property.
 u	 Unicode	        Makes the expression assume individual 
                        characters as code points, not code units, and 
                        thus match 32-bit characters as well.
```
[reference](https://www.codeguage.com/courses/regexp/flags)


### Character Escapes
The backslash (\) in a regular expression indicates one of the following:

The character that follows it is a special character, as shown in the table in the following section. For example, \b is an anchor that indicates that a regular expression match should begin on a word boundary, \t represents a tab, and \x020 represents a space.

A character that otherwise would be interpreted as an unescaped language construct should be interpreted literally. For example, a brace ({) begins the definition of a quantifier, but a backslash followed by a brace (\{) indicates that the regular expression engine should match the brace. Similarly, a single backslash marks the beginning of an escaped language construct, but two backslashes (\\) indicate that the regular expression engine should match the backslash.

[reference](https://docs.microsoft.com/en-us/dotnet/standard/base-types/character-escapes-in-regular-expressions)



## Author
Sheri Brown

[SheriB7](https://github.com/SheriB7)
