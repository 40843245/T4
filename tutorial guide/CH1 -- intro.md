# CH1 -- intro
## objectives

+ introduction of T4

## CH1.1 -- what is T4
`T4` stands for `Text Template Transformation Toolkit`

`T4` is a powerful tool that can easier to write the `text template` and finally generates bean (usually a script written in `C#`) with given `text template`.

First, you can use most of `C#` syntax (such as to use repetive loop (for example `foreach`) to iterate all elements one-by-one) in text template.

Second, `T4` can automatically generate `T-SQL` Query (`.sql` file)

with given `text template` file (`.tt` file) once the text template` file is saved.

Lastly, executing generated `T-SQL` Query can automatically generate beans (usually a script written in `C#`)

in `Visual Studio`.

## pro
Since given T4 template file,

it can generate these in `Visual Studio`.
 
+ `T-SQL` Query (`.sql` file)

+ beans (usually a script written in `C#`)

So, `T4` can offer these pros

+ No manually write a bean

+ Automatically refreshes the bean (refresh when you save `.tt` file and build the project.)

Additionally, it offers these pros 

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