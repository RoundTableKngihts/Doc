#Regular match
##meta chracter
>.	匹配除换行符以外的任意字符
\w	匹配字母或数字或下划线或汉字
\s	匹配任意的空白符
\d	匹配数字
\b	匹配单词的开始或结束
^	匹配字符串的开始
$	匹配字符串的结束

##character escaping
> if you want to use the meta character, you need to add / before them, like /. , /* ....

##repeat
><br>+	重复一次或更多次
?	重复零次或一次
{n}	重复n次
{n,}	重复n次或更多次
{n,m}	重复n到m次

##character class
>use instance: [aeiou] : match one charater in the set of a,e,i,o,u

##branch conditions
>use "|" to match the two match conditions ,like 0\d{2}-\d{8}|0\d{3}-\d{7} can match numbers like : 020-12345678 and 0519-1234567

##antonym
>\W	匹配任意不是字母，数字，下划线，汉字的字符
\S	匹配任意不是空白符的字符
\D	匹配任意非数字的字符
\B	匹配不是单词开头或结束的位置
[^x]	匹配除了x以外的任意字符
[^aeiou]	匹配除了aeiou这几个字母以外的任意字符


##back reference
>