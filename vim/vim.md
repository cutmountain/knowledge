# Vim cheat sheet

Open Vim text editor:

>```console
>(base) me@pc knowledge % vim example.txt
>```

Once the editor opens up:

| Keyboard combination    | Description |
| ----------- | ----------- |
| ESC i  | Enter INSERT mode |
| ESC  | Exit INSERT mode |


Once exited from INSERT mode:

| Keyboard combination    | Description |
| ----------- | ----------- |
| :w INTRO| Save changes |
| :wq INTRO  | Save changes and close file |
| :x INTRO  | Save changes and close file (shortcut for the previous command) |
| :q INTRO  | Close file, without saving |


Open file for editing:

>```console
>(base) me@pc knowledge % vim forloop.sh
>```

After pressing ESC i, type:

>```text
>#!/bin/bash
>for i in 1 2 3
>do
>    echo $i
>done
>```

After saving the file and quiting with :x INTRO, you can execute the file with bash:

>```console
>(base) me@pc knowledge % bash forloop.sh
>```


