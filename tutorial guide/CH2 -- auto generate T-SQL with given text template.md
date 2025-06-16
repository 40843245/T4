# CH2 -- auto generate T-SQL with given text template
## objectives
You will learn how to

+ create a text template

+ auto generate `T-SQL` with given text template

## CH2.1 -- create a text template
> [!TIP]
> It is highly recommended to develop the project with these prequisites
> 
> + latest version of `C#` 
>
> + `LTS` version of `.NET` (`.NET 8.0` or `.NET 9.0` at represent) 
>
> + `Visual Studio 2022` as `IDE`

Create a text template (`.tt`),

it is similar to create a plain `C# script` in `VS`

To do so,

1. Open `Solution Explorer` panel in `VS`,

2. Right click the folder that the text template will be located at.

3. Then select `add` -> `add a new item`

![add a new item.png](add%20a%20new%20item.png)

4. Then it pops a dialog.

![add a new item dialog.png](add%20a%20new%20item%20dialog.png)

In the dialog, enter your file name you want, but with file extension `.tt`.

Then click `OK`.

> [!IMPORTANT]
> The text template file MUST be have file extension `.tt`.

> [!NOTE]
> I highly recommend to give a descriptive name 
>
> to make it easier to read and develop the project. 

## CH2.2 -- auto generate `T-SQL` with given text template
To auto generate `T-SQL` with given text template,

1. Write your code in `.tt` file,

2. After that, save the file.

> [!TIP]
> By default, the keyshortcut to save a file is `CTRL`+`S`.

3. Refresh the changes in Solution Explorer.

4. Then you will see `T-SQL` Query if generated successfully, or 

a simple `error message` if failed.