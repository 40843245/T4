# CH3 -- overview of basic structure in text template
## CH3.1 -- Directive Control Block (`<#@`,`#>`)
1. A Directive Control Block MUST be inside `<#@` and `#>`

For example,

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```

2. There are MUST exactly one directive in `Directive Control Block`.

3. the directives MUST be followed by `<#@` and at least one space.

4. If you need to specify attributes, then

+ each attributes MUST 

be seperated by at least one space.

5. To specify an attribute, the attribute MUST look like following format

```
<attribute-name>="<actually-value>"
```

where

+ `<attribute-name>` is the attribute name that is specified.

It ONLY can be an valid identifier.

    - It can ONLY consist of numeric char, alphabet

    - It MUST start with alphabet.

+ `<actually-value>` is the value that is specified to the attribute name.

    - It can NOT contain any double quotation mark `"`. 
    
    Otherwise, it will cause parse error.

> [!NOTE]
> Not directly specifying attribute is allowed.

> [!NOTE]
> The attributes that are NOT specified will use default value.

For example,

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```

There is a directive.

It uses the directive `template`.

In the directive, 

`debug` attribute is set to `true`.

`hostSpecific` attribute is set to `true`.

`language` attribute is set to `C#`.

## CH3.2 -- Statement Block (`<#`,`#>`)
1. A Statement Block MUST be inside `<#` and `#>`.

2. In Statement Block, one or more statements written in `C#` are allowed.

For example,

```
<#
    // Get all types from the current assembly that are in your model's namespace
    var modelTypes = Assembly.GetExecutingAssembly().GetTypes();
#>
```

## CH3.3 -- Expression Control Block (`<#=`,`#>`)
1. A Expression Control Block MUST be inside `<#=` and `#>`.

2. In Expression Control Block, it can ONLY contain one expression written in `C#`.

For example,

```
<#= DateTime.Now.ToShortTimeString() #>
```

## CH3.4 -- Class Feature Control Block (`<#+`,`#>`)
1. A Class Feature Control Block MUST be inside `<#+` and `#>`.

2. In Class Feature Control Block, you can ONLY add something that should be inside a class definition.
 
Including 

+ methods 

+ properties

+ fields

+ nested classes

For example,

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
<#@ output extension=".txt" #>

<# // ... other logic here #>
<#+
private string GetGreeting()
{
    if (DateTime.Now.Hour < 12)
    {
        return "Good Morning";
    }
    else if (DateTime.Now.Hour < 17)
    {
        return "Good Afternoon";
    }
    else
    {
        return "Good Evening";
    }
}
#>

<# // This is a standard block calling the method from the class feature block #>
<#= GetGreeting() #> World!
```

## CH3.5 -- outside block
The text outside of block will be treated as which type 

according to the type of output (i.e. file extension of file that it will be generated)

> [!IMPORTANT]
> File extension of file that it will be generated
>
> determines by `extension` attribute in `output` directive. 
>
> For example,
>
> ```
> <#@ output extension=".sql" #>
> ```
>
> The generated file will be a SQL Query.
>
> We will disucss it in CH6.

## reference
### Google Gemini
+ [Google Gemini's response -- commonly used block in `T4 Text Template`](https://g.co/gemini/share/6a210f8ffc8a)






