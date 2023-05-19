# Lab Report 3
In this Lab Report I will be exploring the `grep` command within the terminal.

## grep -F command
The `grep -F` command will find a specific word within a text file and output the lines that contain that word. This command also forces the word/pattern you are looking for to act as fixed strings. This command is written as `grep -F "word/pattern you are looking for" filename`. I will now show you this command in use on the file `technical/biomed/1468-6708-3-1.txt`(note that the file being used only has one instance of "Introduction" in the entire file so it will only return one line that contains "Introduction"). Here is an example of this command in action:
```
$ grep -F "Introduction" biomed/1468-6708-3-1.txt
$ Introduction

```
Here is another example of using this command on the file `technical/plos/journal.pbio.0020001.txt`:
``` 
$ grep -F "United States" plos/journal.pbio.0020001.txt
    the number of publications from 1990 until 2000, with the United States contributing the
    most rapidly in the Americas, far outpacing the United States and Canada (Figure 1).
    Canada and United States, the trend in Latin America has been an increase in relative
    21% of the amount invested in United States (RICYT 2002). Indeed, this scientific
    effort compared with that of the United States (2.84%) and Canada (1.5%).
    United States (1.5) and even Canada (3.3) (RICYT 2002). Other countries, such as Costa
    development been increasing in Latin America while decreasing in United States and
    Latin America compared with the relatively flat increases in the United States and Canada,
    United States and Canada. This pattern could be the result of a variety of factors, none of
    scientific collaborations among scientists in Latin America, Europe, and the United States
    United States could reflect a trend towards more costly research in larger scientific
    however, Latin America represented only 6%, while Canada and United States accounted,
    United States contributed somewhat more publications to the top 10 journals (84%) than the
    the United States to the top 10 and top 20 journals was even more pronounced when we
    examined it in respect to worldwide publications. In this case, the United States
    Interestingly, the proportion of publications from Latin America, the United States, and
    versus 6% in the top 20 ecological journals, whereas the United States and Canada had 81%
```
As we can see in the two examples of above the command `grep -F` is useful in finding lines within in a file that contain the specified word that you are looking for. In this case the word your are looking for is case-sensitive and will only output the lines that match the word exactly including if it's upper or lower case.

I found this command-line option on this website [here](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/).

## grep -n command
The `grep -n` command will print the line of that matches the pattern that you are looking for within a file just like the `-F` option, however the `-n` option will also print the line number of the line that contains the pattern you are looking for within a file. The command is written as `grep -n "pattern" filename`. Here is an example of the command with the same pattern and file as we used in the `grep -F` command to show the difference:
```
$ grep -n  "United States" plos/journal.pbio.0020001.txt
51:        the number of publications from 1990 until 2000, with the United States contributing the
61:        most rapidly in the Americas, far outpacing the United States and Canada (Figure 1).
64:        Canada and United States, the trend in Latin America has been an increase in relative
77:        21% of the amount invested in United States (RICYT 2002). Indeed, this scientific
83:        effort compared with that of the United States (2.84%) and Canada (1.5%).
89:        United States (1.5) and even Canada (3.3) (RICYT 2002). Other countries, such as Costa
95:            development been increasing in Latin America while decreasing in United States and
105:        Latin America compared with the relatively flat increases in the United States and Canada,
109:        United States and Canada. This pattern could be the result of a variety of factors, none of
114:        scientific collaborations among scientists in Latin America, Europe, and the United States
117:        United States could reflect a trend towards more costly research in larger scientific
136:        however, Latin America represented only 6%, while Canada and United States accounted,
143:        United States contributed somewhat more publications to the top 10 journals (84%) than the
145:        the United States to the top 10 and top 20 journals was even more pronounced when we
146:        examined it in respect to worldwide publications. In this case, the United States
149:        Interestingly, the proportion of publications from Latin America, the United States, and
156:        versus 6% in the top 20 ecological journals, whereas the United States and Canada had 81%
```
Here is another example of the command being run, this time with a different pattern and file(`technical/biomed/1471-213X-1-6.txt`):
```
$ grep -n "genus" biomed/1471-213X-1-6.txt
27:        garpike, is one of four living species of its genus within
31:        placed a 180 million-year age on the genus, which arose
```
As we can see in the examples above the `grep -n` command is useful in not only finding the lines that contain your specified word within a file, but also the number of the line that contains the word. This can be extremely useful because you can run this command, which will tell you the line number, and then later on if you are possibly reading the text, then you can remember what line the word was on and go directly to that line as you are reading.

I was able to figure out the `grep -n` command by typing `man grep` straight into the command line, which gave me options for `grep` and gave explanations as to what those options do.


