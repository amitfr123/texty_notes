# Knowledge sources
* https://en.wikipedia.org/wiki/Formal_language
* https://en.wikipedia.org/wiki/Regular_language
* https://en.wikipedia.org/wiki/Formal_grammar
* https://introcs.cs.princeton.edu/java/51language/ - information for formal languages.
* https://www2.lawrence.edu/fast/GREGGJ/CMSC515/chapt01/Regular.html - a good and simple explanation for regular language operations.
* https://en.wikipedia.org/wiki/Context-free_language
* https://www.youtube.com/watch?v=5_tfVe7ED3g

# Basic definitions
* Symbol - the basic building block, typically a character or a digit.
* Alphabet - a finite set of symbols.
* Words (strings) - a finite set of a specific alphabet symbols.
* Formal language - a set of assembled strings (derived from the same alphabet) according to a specific set of rules.
* Formal grammar - describes which words are valid according to the language's syntax (rules).

Here are a couple of examples for this definitions:

|        language        |  symbols  |  valid words   | invalid words |
| :--------------------: | :-------: | :------------: | :-----------: |
|        English         | a->z,A->Z |  Hello, World  |     uvbi      |
|         Binary         |    0,1    |   01001,1111   |       -       |
|      Odd integers      |   0->9    |   1,3,21,889   |    2,32,44    |
| Lower case palindromes |   a->z    | aba, aa, czdzc | av,var,hello  |

# Regular language
Regular language is a class of formal languages that can be defined using regular expressions.
###### It should be noted that tools like Yacc Bison and Flex may be used to create regular languages for programming.

Regular languages help us solve 2 problems:
* Specification - how do we have a complete definition for a formal language.
* Recognition - given language **L** and a word **W** how do we check if: $$W\in{L}$$
## Operations
When using regular languages we have a set of basic operations:
* Union
* Complement
* Intersection
* Concatenation
* Closure
### Union
Given 2 regular languages $L_{1}$ and $L_{2}$, then $L=L_{1}\cup{L_{2}}$ is also a regular language.

$$
L_{1} = \{a,ba\}
$$
$$
L_{2} = \{ab,ba,b\}
$$
$$
L=L_{1}\cup{L_{2}} = \{a, ab,ba,b\}
$$
### Complement
If **L** is a regular language, then $\overline{L}$ is also a regular language.

### Intersection
If $L_{1}$ and $L_{2}$ are regular languages, then the new language $L=L_{1}\cap{L_{2}}$ is also a regular language.
### Concatenation
If $L_{1}$ and $L_{2}$ are regular languages, then the concatenation of the two ($L=L_{1}\cdot{L_{2}}$) is a regular language.
$$L=L_{1}\cdot{L_{2}}$$
$$
L = (x|x=x_{i}y_{j}, x_{i}\in{L_{1}}, y_{i}\in{L_{2}})
$$
### Closure (Kleene star)
If $L$ is regular language, then $L^{*}$ is the language comprised of all the possible concatenation 0 or more words.
$$
L = {a,b}
$$
$$
L^{*} = \epsilon\cup L\cup L\cdot L\cup L\cdot L\cdot L\dots
$$
## Generalized regular expressions
In practice regular expressions extend this basic operations and use meta-symbols like: |,*.
By using this meta-symbols we can define regular languages for things like:
* US phone numbers - \\(\[0-9]{3}\\) \[0-9]{3}-\[0-9]{4}

# Context free language
