
# Using the command line

Useful commands to perform programmatically common operations over files
and folders (create, copy, move, delete, download or navigate folders)


## Utilising the ExplainShell interactive command explorer

There is an excellent resource that provides an interactive command
explainer that can be accessed at <https://explainshell.com/>. Feel free
to use and paste the following commands from the tutorial to see an
explanation of the command based on the official commands documentation.

![](explainshell_commands.gif)

## 1. List files in the current folder

Directory is used interchangeably with the term folder.

``` bash
ls -l
```


## 2. Inspect your current folder location in the file system 

To see in which folder you are currently in, use the **`pwd`** command,
short fro **`print working dorectory`**. This will return the absolut
path to the location you currently stand.

> NOTE: What is an *absolut* path? And what is not considered an absolut
> path?

See this resource for a thorough explanation:
<https://www.linuxnix.com/abslute-path-vs-relative-path-in-linuxunix/>

``` bash
pwd
```

## 3. Copy a file 

Duplicate the file content while retaining the initial copy

``` bash
cp README.md duplicated_README.md
```

Now let\'s inspect if the file was created, by listing files in the
directory with the `ls -l` command. We are expecting to view the file
with name `duplicated_README.md` in the listed files and folders

``` bash
ls -l
```

# 4. Deleting a file

To delete (remove) a file we can use the command `rm name_of_folder`.
Let\'s delete the duplicate README.md file named `duplicated_README.md`

Now let\'s inspect if the file was created, by listing files in the
directory with the `ls -l` command. We are expecting to **not** view the
file with name `duplicated_README.md` as we just **deleted** it in the
listed files and folders

``` bash
ls -l
```

## 5. Create a new direcctory (folder)

To create a new folder if that folder doesn\'t exist, we can use the
command `mkdir name_of_folder`. Let\'s create a folder named
`new_folder`
"}
``` bash
mkdir new_folder
```


Now let\'s inspect if the folder was created, by listing files in the
directory with the `ls -l` command. We are expecting to view the folder
with name `new_folder` in the listed files and folders

Let\'s inspect the folder exists with our trusted `ls -l` command

``` bash
ls -l
```


## 6. Delete a folder

We can delete a folder using the `rm -r` command:

``` bash
rm -r new_folder
```

``` bash
ls -l
```


## 7. Downloading a file using a link

We can retrieve a file using a public link. For example, we have
uploaded in a public ZENODO record for this course an example file. The
link for the file is:
<https://zenodo.org/record/4302133/files/deseq2_5k.csv>

``` bash
```

