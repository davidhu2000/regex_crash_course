# A crash course on how to use regular expressions.

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

`=~`is Ruby's basic pattern matching operator, where one side is a string, and the other side is regular expression. This method returns the index of the first match in the string. 

    /adam/.match('madam')   #=> <MatchData 'adam'>
    /yolo/.match('careful') #=> nil

`#match`returns a MatchData object. 

There are other methods that can use regular expression to pattern match. For example, `String#split` and `Array#scan`. 