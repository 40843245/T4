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

+ it will use `C#` compiler to the transformed file by `T4`.

```
<#@ template debug="true" hostSpecific="true" language="C#" #>
```


