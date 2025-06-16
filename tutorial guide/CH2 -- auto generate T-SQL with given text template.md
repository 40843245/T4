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

1. Ensure the `.tt` file property.

Ensure the `custom tool` property is set to `TextTemplatingFileGenerator`.

Ensure the `custom build tool` property is set to `C# builder`.

![custom tool property.png](custom%20tool%20property.png)

2. Write your code in `.tt` file,

> [!CAUTION]
> Check it again and again with caution.
>
> To ensure the these following piece of Blocks are placed in order in `.tt` file.

2.1 

We need to set `C#` compiler will be used to build and then generate transformed file (we will discuss its details in CH8),

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```

2.2 

We also have to set the transformed file has file extension `.sql` (we will discuss its details in CH8)

```
<#@ output extension=".sql" #>
```

2.3 

We also need to load assemblies.

2.3.1 

To load assembly that built in current project (we will discuss its details in CH8),

```
<#@ assembly name="$(TargetPath)" #>
```

2.3.2 

We also need to assemblies that is used for connection of SQL Server,

```
<#@ assembly name="System.Core" #>
<#@ assembly name="System.Data" #>
```

2.4 

We need to generate `import` statement in transformed file (we will discuss its details in CH8),

```
<#@ import namespace="System.Data.SqlClient" #>
```

3. After that, save the file.

> [!TIP]
> By default, the keyshortcut to save a file is `CTRL`+`S`.

4. It will generate `T-SQL` Query with `TextTemplatingFileGenerator` under `.tt` file.

5. Open transformed file, 

you will see `T-SQL` Query if generated successfully, or 

a simple `error message` if failed.