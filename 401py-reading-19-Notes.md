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

### Depth First

+ Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:
  + Pre-order: root >> left >> right
  + In-order: left >> root >> right
  + Post-order: left >> right >> root
