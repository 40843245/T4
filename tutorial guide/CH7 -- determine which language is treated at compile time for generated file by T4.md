# CH7 -- determine which language is treated at compile time for generated file by T4
## objectives
You will learn how to

+ determine which language is treated at compile time for generated file by `T4`

## CH7.1 -- determine which language is treated at compile time for generated file by T4
The `language` attribute of `template` directives 

determines which language is treated at compile time for generated file by T4

For example,

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```

determines that it will use syntax `C#` for generated file by T4.