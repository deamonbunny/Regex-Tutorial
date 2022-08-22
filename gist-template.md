# How to validate Emails with Regex

Here is a tutorial on the use of regex to match emails using the expression `/^([a-z_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,9})$/i`. This can be very helpful when working with email validation in tech such as Node or MongoDB.

## Summary

This tutorial will cover the basics of using regex for email validation through matching. Regex is a regular expression which is a sequence of characters used to define search parameters within code and databases using patterns. Today we will be using `/^([a-z_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,9})$/i` to check emails.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

`/^([a-z_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,9})$/i`

carlmarx@gmail.com
john.doe@hotmail.com
mCarelo@library.edu
flying.p0rKuP1ne@yahoo.com
NotaCop@DefaCop.gov

## Regex Components

### Anchors

The anchors for matching an email using the above example are:
`^ `, which indicates the beginning of the string
`$`to indicate the ending of the string.
It does not include `(m)`, causing the Regex to stop at `$`.

### Quantifiers

Included quantifiers in this regex are `+` which connects together the username + email provider + and site extensions, and `{2,9}` which will limit site extensions to a min of 2 characters and a max of 9 characters.

### OR Operator
 
We are not using or opterators in this tutorial. However an or operator is an expression part that searches for specific options and selects if one of them is caught in the search, and example is `( gov | edu | com )` which would seach for those website endings.

### Character Classes

The only character class we are using in the expression is `\d` which is used to search for single digits from `0-9` in the email providers name.

### Flags

At the end of the expressions outisde of the litteral string indicators `//` we have included `i` which allows us to ignore case sensitivity and and search with a parameter of `[a-z]` instead of `[a-zA-Z]`.

### Grouping and Capturing

This regex expression contains 3 groups consiting of the username `([a-z_\.-]+)`, the address provider `([\da-z\.-]+)` and the site extension `([a-z\.]{2,9})`

### Bracket Expressions

We also use 3 bracket expressions in the 3 groups username `[a-z_\.-]`, the address provider `[\da-z\.-]` and the site extension `[a-z\.]`. Each of these expressions contained within `[]` are searching for anything in a string that matches those characters without case sensitivity due to our `//i` flag.

### Greedy and Lazy Match

This regex uses both greedy and lazy matches. The `+` quantifier acts as a greedy match, taking everything it can from the string before continuing on to the next part of the regex. The groups in the `()` are lazy matching because as soon as the string hits a symbol it does not know it stops and moves on in the regex.

### Boundaries

The boundaries we use are also our anchors `^`, and `$` as they define the start and end of our string.

### Back-references

Like our boundary, `$` is also our back reference,. At the end of the regex we include `$` as it symbolizes the end of the string and also collects everything from its group. Since we have not given `$` a group number to pull it defaults to `$0` and prints the whole thing and stops at that point, thus collecting our whole email.

### Look-ahead and Look-behind

Not using Look Ahead or Look behind

## Author

Find my other work on github at https://github.com/deamonbunny
