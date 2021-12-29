# LEDIP
## a text editor for the KIM-1

There was this small entry on hansotten.nl about a line editor for the KIM-1 called Ledip. Not much infos were given, except some scanned pages of Dr.Dobbs journal issue 29. including the manual and sourcecode Sadly the scans were, well, not very usable. 8 and B and D and 0 were indistinguishable. Litterally. The author of the program, Kiumi Akingbehin, meanwhile Professor at the Michigan University, was so kind to send me another scan. Slightly better, but still far away from being readable.

But I gave it a try anyway and needed like three days to type this little program in and compile it. There were lots of tons of Typos by myself, but with the help of hjm and Hans Otten and their eagle eyes, all errors were found and now this 43 year old piece of software history is revived again, ready to play with.

![LEDIP in action](https://github.com/netzherpes/LEDIP/raw/main/ledip2.jpg)

Instructions: Load the papertape into your KIM-1, clone or the fabulous iOS Emulator "VirtualKIM" Start the Program at place 2000 (mem expansion required) It will now ask for a starting adress, where the text should be stored. any free space is possible, like $3000. This Value is very important later and wil be stored in the Zero Page. MbegL $d5 and MbegH $d6 The End adresses (MendL $d3 and MendH $d4) are updated with every line you type, modify, delete, insert. A lot of Memory shuffeling is going on, when you insert a line in between two existing lines of text: Copy the upfollowing lines exact the ammount of bytes upwards as the inserted text is long and change the end address... Brainfck if you look at the sources. Amazing and perfect RAM saving when memory was rare.

The Folowing commands are accepted:

    Add text with a 4 digit line number: 0010 Hello World!
    *LIST* lists the text with line numbers
    *TEXT* lists the text without line numbers
    *FILE* gives you all needed memory locations to save the text: Zero pages, the program itself and the textarea.
    *EXIT* ... guess.
    *CLEAR* delete everything

LEDIP running

Thanks to: Kiumi Akingbehin, HJM and Hans Otten for their Help,

Have fun, stay childish, Yours Webdoktor

**UPDATE:** let's say you have an existing text on your pc and want to convert it in a way, that LEDIP can process it. The syntax in linux or cygwin is as follows:

    nl -nrz -w4 -s  text_in.txt > text_out.txt

(important are the 2 spaces after -s)

Pro Tipp: Good textfiles can be found [here](http://textfiles.com/sex/EROTICA/)

:P
