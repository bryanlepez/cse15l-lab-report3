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

## grep -c command
The `grep -c` command will give you the amount of lines that match the pattern that you are looking for within a file. You write the command in the following form `grep -c "word/pattern" filename`. Here as an example of the `grep -c` command being ran on the file `technical/911report/chapter-1.txt`:
```
$ grep -c "security" 911report/chapter-1.txt
18
```
Here is another example of the `-c` option being run on the file `technical/government/About_LSC/Comments_on_semiannual.txt`:
```
$ grep -c "legal" government/About_LSC/Comments_on_semiannual.txt
35
```
As we can see above the `grep -c` command's output is the amount of lines that contain the pattern that we are looking for within the file. Eighteen lines in the `technical/911report/chapter-1.txt` file contained "security" so that is the output of the command. Similarly, 35 lines contained "legal" in the `government/About_LSC/Comments_on_semiannual.txt` so the output was 35. This could be useful because it let's you know how many times a word is mentioned in the text by line. 

I was able to learn about this command by asking ChatGPT. The prompt I used was "What are some command-line options for grep". ChatGPT then gave me a list of command-line options in which I chose `grep -c`.

## grep -r command
The `grep -r` command gives you a lot of information at one time. This command is able to go through the a directory and its subdirectories recursively in order to find the pattern/word you are looking for. This command outputs the lines that contain the pattern you are looking for and outputs those lines along with the path that they are stored in. The command is written likes this `grep -r "pattern/word" directory`. Here is an example of looking for "Introduction" in the "government" directory:
```
$ grep -r "Introduction" government
government/About_LSC/Progress_report.txt:Introduction (purpose of the manual, how to use it,
government/About_LSC/Strategic_report.txt:Introduction
government/About_LSC/reporting_system.txt:Introduction
government/About_LSC/conference_highlights.txt:Introduction
government/Env_Prot_Agen/jeffordslieberm.txt:1. Introduction
government/Env_Prot_Agen/nov1.txt:Introduction 
government/Env_Prot_Agen/tech_adden.txt:As noted in Section I (Introduction), we present Base and
government/Gen_Account_Office/d0269g.txt:Introduction
government/Gen_Account_Office/d0269g.txt:Introduction
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:items. As the Board stated in the Introduction and Background
government/Gen_Account_Office/pe1019.txt:Introduction
government/Gen_Account_Office/gg96118.txt:Introduction
government/Gen_Account_Office/gg96118.txt:Introduction
government/Gen_Account_Office/d01121g.txt:Introduction to Investigations in an Electronic
government/Gen_Account_Office/d01121g.txt:Electronic Law Enforcement: Introduction to Investigations in an
government/Gen_Account_Office/d03273g.txt:Section 1: Introduction
government/Gen_Account_Office/d03273g.txt:Section 1: Introduction
government/Gen_Account_Office/InternalControl_ai00021p.txt:Introduction
government/Gen_Account_Office/im814.txt:Introduction
government/Gen_Account_Office/ai9868.txt:basic concepts and techniques entitled An Introduction to Computer
government/Gen_Account_Office/May1998_ai98068.txt:basic concepts and techniques entitled An Introduction to Computer
government/Gen_Account_Office/d02701.txt:Introduction
government/Gen_Account_Office/ai2132.txt:Introduction
government/Gen_Account_Office/ai2132.txt:Introduction
government/Post_Rate_Comm/Mitchell_spyros-first-class.txt:Introduction
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:A. Introduction
government/Post_Rate_Comm/Mitchell_6-17-Mit.txt:Introduction
government/Post_Rate_Comm/Cohenetal_Scale.txt:Introduction
government/Post_Rate_Comm/Cohenetal_Scale.txt:Campbell, James I., Jr., "An Introduction to the History of the
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:1. Introduction
```
Here is another example of `grep -r`, this time we are looking for the pattern "machine" in the "plos" directory:
```
$ grep -r "machine" plos
plos/journal.pbio.0020430.txt:        Spider-Man comic, is the ultimate characterization of a brain–machine
plos/journal.pbio.0020430.txt:        who dreams of harnessing nuclear fusion. The machine is a harness of four mechanical arms
plos/journal.pbio.0020430.txt:        machine and the brain is at the spinal cord level, with an “inhibitor chip” to prevent the
plos/journal.pbio.0020430.txt:        while the inhibitor chip is disabled, resulting in the machine gaining partial control of
plos/journal.pbio.0020430.txt:        his brain. Unable to subvert the machine to his will and conscience, Octavius, together
plos/journal.pbio.0020430.txt:        the evil machine and save the world.
plos/journal.pbio.0020430.txt:        BMI would be fed with both brain and machine control signals; the intention of movement
plos/journal.pbio.0020430.txt:        BMI? In the movie, Octavius's crisis is a severe unbalance in favor of machine control.
plos/journal.pbio.0020430.txt:        For both science and science fiction, the question is the same. Brain and machine: which
plos/journal.pbio.0020394.txt:        developments in artificial intelligence, machine learning, computer vision, and a host of
plos/journal.pbio.0020150.txt:        by the imaging machinery.
plos/journal.pbio.0020150.txt:        The resolution of the best fMRI machines—the smallest “volume picture element,” or
plos/journal.pbio.0020190.txt:        recombination machinery has been partly co-opted for chromosome alignment in some
plos/journal.pbio.0030050.txt:        mainframe machine, he suggests.
plos/journal.pbio.0020133.txt:        viruses. Did the RNAi machinery also generate small RNAs for host gene regulation?
plos/journal.pbio.0020133.txt:        caliper to sequester short RNAs from the silencing machinery (Vargason et al. 2003). A
plos/journal.pbio.0020053.txt:        employed combinatorial biosynthesis to learn how to use part of the machinery for
plos/journal.pbio.0030065.txt:        curators' domain knowledge into a structured training set for the purposes of machine
plos/pmed.0020018.txt:          The identification of the regulatory components of the ectodomain shedding machinery
plos/journal.pbio.0030076.txt:        numerous machineries of the infected cell. Thus, studies of their replicative cycles have
plos/journal.pbio.0030076.txt:        cell machinery, lentiviruses code for additional accessory and regulatory proteins that act
plos/journal.pbio.0030076.txt:        polyadenylation machineries, and the conversions of DSIF and NELF into elongation factors.
plos/journal.pbio.0020073.txt:        As an example of highly successful machines at the “small scale,” Feynman prompted his
plos/journal.pbio.0020073.txt:        “machines” that power biological cells (Drexler 1986). These “machines” are inherently
plos/journal.pbio.0020073.txt:        to novel rotary machines that function as molecular motors for a variety of nanoscale
plos/journal.pbio.0020073.txt:        In order to fully exploit these nanoscale protein machines, it is of prime importance to
plos/journal.pbio.0020073.txt:        to consider the construction of an ordered array of ATP synthase driven nanomachines, each
plos/journal.pbio.0020073.txt:        gearing systems. Construction of such systems may facilitate the design of machines that
plos/journal.pbio.0020073.txt:        in response to environmental stimuli may facilitate the design of nanoscale machines that
plos/journal.pbio.0020073.txt:        movable machines? They may or may not be useful, but they surely would be fun to make.”
plos/pmed.0010056.txt:        scrounge resources from university machines or borrow time on home computers [16, 17]. This
plos/journal.pbio.0020164.txt:        components of each other's signaling machinery.
plos/journal.pbio.0020213.txt:        understanding this machinery is the way to devise new control measures that could give
plos/journal.pbio.0020013.txt:        protein-eating machine hints at the exquisite controls that must rgulate its function.
```
As you can see above the `grep -r` command is extremely useful as it gives us a ton of information at one time. It allows us to search within multiple all at once while the previously mentioned commands are looking in just one file. This can save a lot of time in looking for things at a larger scale. Not only does it output the lines that match your pattern, but it also tells us where that line is stored.

I was able to find this command-line option for `grep` by, once again, doing `man grep` in the command line. This popped up with the manual screen for grep which helped me find the `grep -r` command as well as an explantion of what it does.


