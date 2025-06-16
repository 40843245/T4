# CH4 -- comments in text template
## CH4.1 -- comments in Statement Block (`<#`,`#>`) for generating script written in `C#`
Since Statement Block (`<#`,`#>`) can ONLY contain statements written in `C#`, 

we can use `C#` comments the comment these text,

making the commentted code does NOT be executed.

+ `//`: a single line comment that comments the text after it.

+ `/*`,`*/`: a multiple line comment that comments

the text inside `/*` and `*/`.

## CH4.2 -- comments in Class Feature Blocks (`<#+`,`#>`) for generating script written in `C#`
Since you can ONLY add something that should be inside a class definition,

we can use `C#` comments the comment these text.

+ `//`: a single line comment that comments the text after it.

+ `/*`,`*/`: a multiple line comment that comments

the text inside `/*` and `*/`.

## CH4.3 -- Outside of Block for generating script written in `C#`
Use `T-SQL` Query comments (single line comment) to
 
comment the text that are outside of block.

+ `--`: a single line comment that comments the text after it.

For example,

```
-- Generated SQL for LocalDB database
-- Created: <#= DateTime.Now #>
```

## CH4.4 -- HTML block for generating file written in `html`
Similar to native html,

use standard html comments \`\` that comments the single line starts with \`\`

## reference
### Google Gemini
+ [Google Gemini's response -- comments in T4 Text Template](https://g.co/gemini/share/c1486dca6f66)