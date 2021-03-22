---
id: csharp-coding-conventions
title: C# Coding Conventions
---

Our C# coding conventions are inspired from  [Google's Style Guide](https://google.github.io/styleguide/csharp-style.html),
and from the [.NET Framework Design Guidelines](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines).


## Overview & Coding approach
- Keep lines short and not expand beyond the 90th column. Prefer
short sentences as you would when writing free text.
- Respect your surroundings: make sure that you've established a good
understanding of a project's conventions and follow them.
- Be "conservative" before introducing new technologies (libraries, frameworks etc) to a project. 
Be certain that it will further help development and achieve consent before you introduce them.
- Pierce through the abstraction layer of the things you use. Try and understand how your 
tools (libraries, frameworks etc) work.
- Pay attention when naming things. Be clear and concise.
- Examine your changes carefully before [submitting your code](doc1#commiting-your-work) (commit).
- Always code as if your code is meant to be read by someone else.

> _Programs are meant to be read by humans and only incidentally for computers to execute_
>
> _Donald Knuth_



## Naming
- Use **PascalCase** for names of classes, methods, enumerations, public fields, public properties, namespaces.

- Names of interfaces start with `I`, *e.g.* `IInterface`.

- Use **camelCase** for names of local variables and function parameters.

- Prefix private class members/fields with _underscore_. E.g.
`private bool _myPrivateField`.

- Use **PascalCase** for Filenames and directory names. E.g. `MyFile.cs`.

### Namespaces
- Namespaces should be no more than 2 levels deep.
- Don't force file/folder layout to match namespaces.
- Top-level namespace names must be globally unique and recognizable.

## New lines
Use a new line character before opening curly brackets (`{}`) only for
classes, interfaces, structs & function bodies.
Do not add new lines before opening brackets to `if/else`, `for/foreach/while`, class instantiations or anonymous types declarations.

## Whitespace
- Add space after commas.
- Add a space character between:
    1) a unary operator and its operand.
    2) the operator and each operand of all other operators.
- Do **not add** spaces after an opening parenthesis or before a closing parenthesis. 
- Line continuations are indented 4 spaces.
- **No** trailing spaces.

_Example_
```csharp
// Bad
using System;
namespace projectName.src.domain.Services {
    public class Projectservice : iProjectService 
    {
        private readonly dBContext DBContext;

        public Projectservice(dBContext dbcontext)
        {
            DBContext = dbcontext;
        }

        public bool getStatus(bool status) { 
       
            if(status == null)
            {
                throw new ArgumentNullException(
                    nameof(status)
                    );
            }
        }
    }
}
```
```C#
// Good
using System;

// Keep XML comments as a visual aid, clearly separating
// members between one another (suggestion).
namespace ProjectName.Services
{
    /// <summary>
    /// 
    /// </summary>
    public class ProjectService : IProjectService
    {
        /// <summary>
        /// 
        /// </summary>
        private readonly DbContext _dbContext;

        /// <summary>
        /// 
        /// </summary>
        public bool Status { get; set; }

        /// <summary>
        /// 
        /// </summary>
        private bool _active { get; set; }

        /// <summary>
        /// 
        /// </summary>
        /// <param name="dbContext"></param>
        public ProjectService(
            DbContext dbContext)
        {
            _dbContext = dbContext;
        }

        /// <summary>
        /// 
        /// </summary>
        /// <returns></returns>
        public void Save()
        { 
            try {
                if (_dbContext.SaveChanges() > 0 ) {
                    // no new lines to `if`s opening bracket
                } else {

                }
            } catch(Exception) {
                // log
            }
        }
    }
}
```

## Async
- Prefer `async` methods where possible.
- Use `async` suffix to methods that return `Task`.

_Example_
```csharp
// Bad
public async Task SendEmail(Options options);
```
```csharp
// Good
public async Task SendEmailAsync(Options options);
```

## Use `var`

- Use `var` instead of declaring the full type's name for simplicity.

_Example_
```csharp
// Bad
List<Customer> customers = new List<Customer>();
bool customerExists = true;
```

```csharp
// Good
var customers = new List<Customer>();
var customerExists = true;
```
