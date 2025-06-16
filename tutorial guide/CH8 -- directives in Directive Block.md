# CH8 -- directives in Directive Block
## objectives
You will learn

+ some commonly used directives in Directive Block

## CH8.1 -- `template`

| attribute | meaning | description | notes | notice
| :-- | :-- | :-- |
| `language` | `language` | determines which compiler of programming language will be used to compile the generated file. | | |
| `debug` | `debugging information` | determines whether instructs the `T4` engine to generate debugging information for the transformed code. | | |
| `hostSpecific` | specific host | determines whether `T4` template needs to interact with the host application that's running the transformed code | When `hostSpecific` is `"true"`,<br> a property called `Host` is made available within your template.<br> This `Host` property provides access to services and information from the environment (the "host") where the template is being executed. | |

### examples
#### example 1

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```

The above example indicates that

+ In `language="C#`, it will use `C#` compiler to the transformed file by `T4`.

+ In `debug="true"`, the debugging information will appear in transformed file by `T4`.

+ In `hostSpecific="true"`, `T4` template needs to interact with the host application that's running the transformed file by `T4`.

#### example 2

```
<#@ template debug="true" hostSpecific="false" language="C#" #>
```

The above example indicates that

+ In `language="C#`, it will use `C#` compiler to the transformed file by `T4`.

+ In `debug="true"`, the debugging information will appear in transformed file by `T4`.

+ In `hostSpecific="false"`, `T4` template does NOT need to interact with the host application that's running the transformed file by `T4`.

> [!IMPORTANT]
> When can we specify `hostSpecific="false"?
> 
> + we're running the template outside of a specific host, or 
>
> + we don't need to interact with the host.

### reference
#### Google Gemini
+ [Google Gemini's response -- explanation of `template` directives](https://g.co/gemini/share/5f8d85545c07)

## CH8.2 -- `output`

| attribute | meaning | description | notes | notice
| :-- | :-- | :-- |
| `extension` | `file extension` | `T4` engine will generate the transformed file with specified file extension. | | |

### examples
#### example 1

```
<#@ output extension=".sql" #>
```

indicates that the `T4` engine will generate a transformed file the ends with `.sql`.

### further reading
#### Google Gemini
+ About commonly used file extension, see

[Google Gemini's response -- explain the directive output in Text template](https://g.co/gemini/share/51232635d567)

+ About scenario, see [Google Gemini's response -- explain the directive output in Text template](https://g.co/gemini/share/51232635d567)

## CH8.3 -- `assembly`

| attribute | meaning | description | notes | notice
| :-- | :-- | :-- |
| `name` | assembly name to be loaded | tell `T4` engine this assembly needs to be loaded. | it can be either <ul><li>a `strong name`</li><li>`simple name`</li><li>file name (relative path or absoletely path)</li>| |

> [!NOTE]
> Quick Review of ways to represent a assembly to be loaded:
>
> + a strong name of an assembly refers a string that 
>
> contains assembly name and its details 
>
> (e.g. `System.Xml, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`)
>
> + a simple name refers a string that 
>
> ONLY contains assembly name
> 
> (e.g. `System.Core`)
>
> + a file path refers a string that 
>
> the assembly locates at
>
> (e.g. `C:\MyProject\bin\Debug\MyAssembly.dll`)

> [!IMPORTANT]
> `TargetPath` is a macro for building with `MSBuild`.
>
> It stores the full path of the target assembly being built by the current project.

> [!IMPORTANT]
> The syntax `$(`,`)` in `text template` is used to
> 
> access the properties of macro in `MSBuild`.
> 
> For example,
>
> `$(TargetPath)` will access the full path of the target assembly being built by the current project.
>
> then expand it by `MSBuild`


> [!NOTE]
> `MSBuild` is used for building script written in `C#`.
>
> `MSBuild.exe` is an execute file that is used for building script written in `C#`.

### reference
#### Google Gemini

[Google Gemini's response -- explain assembly directives in T4 Text Template](https://g.co/gemini/share/b686527ffc6f)

### further reading
#### Google Gemini

+ About `$(`,`)` syntax, see 

[Google Gemini's response -- What does `$(...)` syntax mean in T4 Text Template?](https://g.co/gemini/share/656934648874)

+ About `TargetPath` macro, see

[Google Gemini's response -- explain assembly directives in T4 Text Template](https://g.co/gemini/share/b686527ffc6f)

##