# Guide to Regex

This comprehensive tutorial covers all aspects of regex. Use the table of contents to navigate to different sections of the guide.

## Summary

Regular expressions, or regex for short, are powerful tools for validating strings to ensure they contain specific letters, numbers, or phrases.

Here’s an example of a regex pattern used to match an email address:

scss
Copy code
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents
Anchors
Quantifiers
OR Operator
Character Classes
Flags
Grouping and Capturing
Bracket Expressions
Greedy and Lazy Match
Boundaries
Back-references
Look-ahead and Look-behind

## Regex Components
A regex pattern must be enclosed in forward slashes (/) and comprises various components. These components include anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. Below, we will delve into each of these components.

## Anchors
The anchor characters are ^ and $.

The ^ anchor signifies that a string begins with the characters immediately following it:
Exact string matching: ^Bob matches strings like "Bob" or "Bob likes pie," but not "bob" or "bob likes pie."
A range of possible options displayed using bracket expressions, which we'll cover further down the line.
The $ anchor signifies that a string ends with the characters immediately preceding it. This can be used in a similar manner to the ^ anchor.
Quantifiers
Quantifiers determine the number of characters a regex pattern can match, often specifying a minimum and maximum number of characters. Quantifiers are placed just before the $ anchor. For example, {2,6}$ specifies a minimum of 2 and a maximum of 6 characters.

## Quantifiers 

are greedy by default, meaning they match as many occurrences of the pattern as possible. The primary quantifiers include:

— Matches zero or more times.
— Matches one or more times.
? — Matches zero or one time.
{} — Curly brackets specify limits in three ways:
{n} — Matches exactly n times.
{n,} — Matches at least n times.
{n,x} — Matches between n and x times.
Any quantifier can be made lazy by adding the ? operator after it, which matches as few occurrences as possible.

## Grouping and Capturing
Grouping constructs, defined by parentheses (), are used to group parts of a regex pattern together.

In our email-matching regex, there are three main grouped parts of the pattern:

The Username Grouping: ([a-z0-9_.-]+)
Specifies that any lowercase letter (a-z), any digit (0-9), and the special characters _, ., and - are acceptable before the @ sign in an email address.
The Domain Grouping: ([\da-z.-]+)
Determines the domain name of the email, allowing digits, lowercase letters, periods, and hyphens.
The TLD Grouping: ([a-z.]{2,6})
Specifies the Top-Level Domain (TLD) of the email address, such as .com, .org, or .net, allowing for 2 to 6 characters.
Bracket Expressions
Bracket expressions, represented by square brackets [], define a range of characters to match and are also known as positive character groups. These expressions can be customized to match any desired characters. For example, [xyz] matches any string containing 'x', 'y', or 'z'.

## Bracket expressions 

often use a hyphen to denote a range of characters. For instance, [a-z0-9] includes any lowercase letter from 'a' to 'z' and any digit from '0' to '9'. Therefore, [xyz] is equivalent to [x-z].

Let's break down the regex statement [a-z0-9_.-]:

[a-z] — Allows any lowercase letter from 'a' to 'z'.
[0-9] — Allows any digit from '0' to '9'.
[_.-] — Allows underscores _, periods ., and hyphens -.
Character Classes
Character classes are segments of code within the grouping construct parentheses.

The Username Character Class: [a-z0-9_.-]
Matches any lowercase letter (a-z), any digit (0-9), and the special characters _, ., and -.
The Domain Character Class: [\da-z.-]
Matches any digit (\d), any lowercase letter (a-z), periods (.), and hyphens (-).
The TLD Character Class: [a-z.]{2,6}
Matches any lowercase letter (a-z) and periods (.), with a length of 2 to 6 characters.
Author