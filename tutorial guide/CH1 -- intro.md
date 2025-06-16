# CH1 -- intro
## objectives

+ introduction of T4

## CH1.1 -- what is T4
`T4` stands for `Text Template Transformation Toolkit`

`T4` is a powerful tool that can easier to write the `text template` and finally generates bean (usually a script written in `C#`) with given `text template`.

You can determine which programming language will be used for generated file by `T4` (we will discuss it in CH7).

Additionally, you also can determine the file extension of generated file by `T4` (we will discuss it in CH6).

So there is a way to generate bean (a script written in `C#`) with given `text template`.

First, set the generated file as `.sql`.

```
<#@ output extension=".sql" #>
```

We will discuss more details in CH6.

Second, set the `C#` language is used for generated file.

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```

We will discuss more details in CH7.

Then, you can use `C#` syntax (such as to use repetitive loop (for example `foreach`) to iterate all elements one-by-one) in text template.

After finishing your text template and save it, 

`T4` will automatically generate `T-SQL` Query (`.sql` file) that

Lastly, executing generated `T-SQL` Query can automatically generate beans (usually a script written in `C#`)

## pro
The main pro of `text template` file and `T4`.

+ you can customize the file extension of generated file by `T4 `easily with a `text template` file (we will discuss it in CH6)
 
+ you can customize the which compiler of programming language will be used for generated file by `T4` easily with a `text template` file (we will discuss it in CH7)

So we can imply that, `T4` also offer these pros

+ No manually write a bean

+ Automatically refreshes the bean (refresh when you save `.tt` file and build the project.)

+ writing `text template` is easier than writing html 

+ writing `text template` can save lots of time (than it).

## cons
However,

+ it is harder to learn than `T-SQL` Query 

(even you are familar with `T-SQL` Query, 

`C#`, and

the core concept and design of programming such as `namespace` and `OOP` design pattern).

+ its learning curve might be slower

## reference
### docs
+ [Code Generation and T4 Text Templates](https://learn.microsoft.com/en-us/visualstudio/modeling/code-generation-and-t4-text-templates?view=vs-2022)