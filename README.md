# A crash course on how to use regular expressions

**NB:** this crash course uses Ruby as the default language.

Regular expressions are used to match patterns in strings. This repo serves as a crash course on how to use regular expression.

## Creating a regex object

There are three ways to create a `regex` object.

    /.../
    %r{...}
    Regexp.new(...)

where `...` is the desired pattern.

## Methods

    'hello' =~ /world/ #=> nil
    'banana' =~ /ana/  #=> 1

`=~` is Ruby's basic pattern matching operator, where one side is a string, and the other side is regular expression. This method returns the index of the first match in the string.

    /adam/.match('madam')   #=> <MatchData 'adam'>
    /yolo/.match('careful') #=> nil

`#match` returns a MatchData object.

There are other methods that can use regular expression to pattern match. For example, `String#split` and `Array#scan`.

## Characters Classes

| character | function                                 |
|:---------:|------------------------------------------|
|    `.`    | any single character except new line     |
|  `[abc]`  | any character in the set                 |
| `[^abc]`  | any character not in the set             |
|  `[a-z]`  | any character from `a` to `z`.           |
|   `\w`    | any word character `[a-zA-Z0-9_]`        |
|   `\W`    | any non-word character   `[^a-zA-Z0-9_]` |
|   `\d`    | any digit character `[0-9]`              |
|   `\D`    | any non-word character   `[^0-9]`        |
|   `\s`    | a whitespace character                   |
|   `\S`    | any non-word character                   |
|   `\h`    | a hexdigit character `[0-9a-fA-F]`       |
|   `\H`    | a non-hexdigit character `[^0-9a-fA-F]`  |

### Escaped Special Characters

These characters have special meanings in regular expressions and needs to be escaped if you want to match that exact character.

`\.`, `\\`, `\*`, `\+`, `\?`
