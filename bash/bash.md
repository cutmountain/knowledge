# Bash cheat sheet

Create directory:

>```console
>(base) me@pc ~ % mkdir knowledge  
>```

Navigate to directory:

>```console
>(base) me@pc ~ % cd knowledge  
>```

Navigate upwards to parent directory:

>```console
>(base) me@pc ~ % cd ..  
>```

Navigate upwards to home directory:

>```console
>(base) me@pc ~ % cd ~  
>```

Show directory contents:

>```console
>(base) me@pc knowledge % ls -l  
>```

Show directory contents including **hidden files** (in the list, hidden files will start with a dot .):

>```console
>(base) me@pc knowledge % ls -la 
>```

Create file:

>```console
>(base) me@pc knowledge % touch example
>```

Rename file (e.g. to add the ".txt" file extension we forgot when creating the file):

>```console
>(base) me@pc knowledge % mv example example.txt
>```

Open Vim text editor (NB See folder /vim in this repository for instructions on how to use Vim):

>```console
>(base) me@pc knowledge % vim example.txt
>```

Show file contents:

>```console
>(base) me@pc knowledge % cat example.txt
>```

Show file contents, with pagination:

>```console
>(base) me@pc knowledge % less example.txt
>```
*[N.B. Type :q to exit paginator]*

Find contents in a file:

>```console
>(base) me@pc knowledge % grep "Hello" example.txt
>```

Find files, by name, in current directory:

>```console
>(base) me@pc knowledge % find . -name example.txt
>```

Delete file:

>```console
>(base) me@pc knowledge % rm example.txt
>```

Execute file:

>```console
>(base) me@pc knowledge % bash forloop.sh
>```