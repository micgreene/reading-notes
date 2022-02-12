# Automation

## Regular Expressions in Python
+ In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this module with the help of import:
+ import re

## Basic Patterns: Ordinary Characters
+ `pattern = r"Cookie"`
+ `sequence = "Cookie"`
+ `if re.match(pattern, sequence):`
+ `print("Match!")`
+ `else: print("Not a match!")`

### Wild Card Characters: Special Characters

+ **.search()**
  + With the search function, you scan through the given string/sequence, looking for the first location where the regular expression produces a match.
+ **.group()**
  + The group function returns the string matched by the re.
+ **.** - A period. Matches any single character except the newline character.
  + `re.search(r'Co.k.e', 'Cookie').group()`
+ **^** - A caret. Matches the start of the string.
  + `re.search(r'^Eat', "Eat cake!").group()`
+ **$** - Matches the end of string.
  + `re.search(r'cake$', "Cake! Let's eat cake").group()`
+ **[abc]** - Matches a or b or c.
+ **[a-zA-Z0-9]** - Matches any letter from (a to z) or (A to Z) or (0 to 9)
  + `re.search(r'[0-6]', 'Number: 5').group()`

### \ - Backslash

  + If the character following the backslash is a recognized escape character, then the special meaning of the term is taken
    + re.search(r'Not a\sregular character', 'Not a regular character').group()
  + Else if the character following the \ is not a recognized escape character, then the \ is treated like any other character and passed through
    + re.search(r'Just a \regular character', 'Just a \regular character').group()
  + \ can be used in front of all the metacharacters to remove their special meaning
    + re.search(r'Just a \\sregular character', 'Just a \sregular character').group()

### There is a predefined set of special sequences that begin with '\'

  + **\w** - Lowercase 'w'. Matches any single letter, digit, or underscore.
  + **\W** - Uppercase 'W'. Matches any character not part of \w (lowercase w).
    + print("Lowercase w:", re.search(r'Co\wk\we', 'Cookie').group())
  + **\s** - Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return.
  + **\S** - Uppercase 'S'. Matches any character not part of \s (lowercase s).
  + **\d** - Lowercase d. Matches decimal digit 0-9.
  + **\D** - Uppercase d. Matches any character that is not a decimal digit.
  + **\t** - Lowercase t. Matches tab.
  + **\n** - Lowercase n. Matches newline.
  + **\r** - Lowercase r. Matches return.
  + **\A** - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.
  + **\Z** - Uppercase z. Matches only at the end of the string.
    + **^ and \A are effectively the same, and so are $ and \Z. Except when dealing with MULTILINE mode*
  + **\b** - Lowercase b. Matches only the beginning or end of the word.

### Repetitions
+ The re module handles repetitions using the following special characters:
+ **+** - Checks if the preceding character appears one or more times starting from that position.
  + `re.search(r'Co+kie', 'Cooookie').group()`
+ * - Checks if the preceding character appears zero or more times starting from that position.
  + `re.search(r'Ca*o*kie', 'Cookie').group()`
+ **?** - Checks if the preceding character appears exactly zero or one time starting from that position.
  + `re.search(r'Colou?r', 'Color').group()`
+ **{x}** - Repeat exactly x number of times.
+ **{x,}** - Repeat at least x times or more.
+ **{x, y}** - Repeat at least x times but no more than y times.
  + `re.search(r'\d{9,10}', '0987654321').group()`
