---
title: "Variables and Assignment"
teaching: 8
exercises: 4
questions:
- "How can I store data in programs?"
objectives:
- "Write programs that assign scalar values to variables and perform calculations with those values."
- "Correctly trace value changes in programs that use scalar assignment."
keypoints:
- "Use variables to store values."
- "Use `print` to display values."
- "Variables must be created before they are used."
- "Variables can be used in calculations."
- "Use an index to get a single character from a string."
- "Use a slice to get a substring."
- "Use the built-in function `len` to find the length of a string."
- "Python is case-sensitive."
- "Use meaningful variable names."
---
## Use variables to store values.

*   **Variables** are names for values.
*   In Python the `=` symbol assigns the value on the right to the name on the left.
*   The variable is created when a value is assigned to it.
*   Here, Python assigns an age to a variable `age`
    and a name in quotes to a variable `first_name`.

    ~~~
    age = 42
    first_name = 'Ahmed'
    ~~~
    {: .language-python}

*   Variable names
    * can **only** contain letters, digits, and underscore `_` (typically used to separate words in long variable names)
    * cannot start with a digit
    * are **case sensitive** (age, Age and AGE are three different variables)
*   Variable names that start with underscores like `__alistairs_real_age` have a special meaning
    so we won't do that until we understand the convention.

## Use `print` to display values.

*   Python has a built-in function called `print` that prints things as text.
*   Call the function (i.e., tell Python to run it) by using its name.
*   Provide values to the function (i.e., the things to print) in parentheses.
*   To add a string to the printout, wrap the string in single or double quotes.
*   The values passed to the function are called **arguments**

~~~
print(first_name, 'is', age, 'years old')
~~~
{: .language-python}
~~~
Ahmed is 42 years old
~~~
{: .output}

*   `print` automatically puts a single space between items to separate them.
*   And wraps around to a new line at the end.

## Variables must be created before they are used.

*   If a variable doesn't exist yet, or if the name has been mis-spelled,
    Python reports an error. (Unlike some languages, which "guess" a default value.)

~~~
print(last_name)
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-1-c1fbb4e96102> in <module>()
----> 1 print(last_name)

NameError: name 'last_name' is not defined
~~~
{: .error}

*   The last line of an error message is usually the most informative.
*   We will look at error messages in detail [later]({{ page.root }}/15-scope/#reading-error-messages).

## Variables can be used in calculations.

*   We can use variables in calculations just as if they were values.
    *   Remember, we assigned the value `42` to `age` a few lines ago.

~~~
age = age + 3
print('Age in three years:', age)
~~~
{: .language-python}
~~~
Age in three years: 45
~~~
{: .output}

## Use an index to get a single character from a string.

*   The characters (individual letters, numbers, and so on) in a string are
    ordered. For example, the string `'AB'` is not the same as `'BA'`. Because of
    this ordering, we can treat the string as a list of characters.
*   Each position in the string (first, second, etc.) is given a number. This
    number is called an **index** or sometimes a subscript.
*   Indices are numbered from 0.
*   Use the position's index in square brackets to get the character at that
    position.

![an illustration of indexing](../fig/2_indexing.svg)

~~~
atom_name = 'helium'
print(atom_name[0])
~~~
{: .language-python}
~~~
h
~~~
{: .output}

## Use a slice to get a substring.

*   A part of a string is called a **substring**. A substring can be as short as a
    single character.
*   An item in a list is called an element. Whenever we treat a string as if it
    were a list, the string's elements are its individual characters.
*   A slice is a part of a string (or, more generally, any list-like thing).
*   We take a slice by using `[start:stop]`, where `start` is replaced with the
    index of the first element we want and `stop` is replaced with the index of
    the element just after the last element we want.
*   Mathematically, you might say that a slice selects `[start:stop)`.
*   The difference between `stop` and `start` is the slice's length.
*   Taking a slice does not change the contents of the original string. Instead,
    the slice is a copy of part of the original string.

~~~
atom_name = 'sodium'
print(atom_name[0:3])
~~~
{: .language-python}
~~~
sod
~~~
{: .output}

## Use the built-in function `len` to find the length of a string.

~~~
print(len('helium'))
~~~
{: .language-python}
~~~
6
~~~
{: .output}

*   Nested functions are evaluated from the inside out,
     like in mathematics.

## Python is case-sensitive.

*   Python thinks that upper- and lower-case letters are different,
    so `Name` and `name` are different variables.
*   There are conventions for using upper-case letters at the start of variable names so we will use lower-case letters for now.

## Use meaningful variable names.

*   Python doesn't care what you call variables as long as they obey the rules
    (alphanumeric characters and the underscore).

~~~
flabadab = 42
ewr_422_yY = 'Ahmed'
print(ewr_422_yY, 'is', flabadab, 'years old')
~~~
{: .language-python}

*   Use meaningful variable names to help other people understand what the program does.
*   The most important "other person" is your future self.

> ## Predicting Values
>
> What is the final value of `position` in the program below?
> (Try to predict the value without running the program,
> then check your prediction.)
>
> ~~~
> initial = 'left'
> position = initial
> initial = 'right'
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > 'left'
> > ~~~
> > {: .output}
> >
>> The `initial` variable is assigned the value `'left'`.
> > In the second line, the `position` variable also receives
>> the string value `'left'`. In third line, the `initial` variable is given the
>> value `'right'`, but the `position` variable retains its string value
>> of `'left'`.
>{: .solution}
{: .challenge}

> ## Slicing practice
>
> What does the following program print?
>
> ~~~
> atom_name = 'carbon'
> print('atom_name[1:3] is:', atom_name[1:3])
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > atom_name[1:3] is: ar
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}
