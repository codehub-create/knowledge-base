# C# Coding Conventions

#### Our C# coding conventions are inspired from  [C# at Google Style Guide](https://google.github.io/styleguide/csharp-style.html) .

# Formatting rules

## Naming
- Names of classes, methods, enumerations, public fields, public properties, namespaces: **PascalCase**.

- Names of interfaces start with `I`, *e.g.* `IInterface`.

- Names of local variables, parameters: **camelCase**.

- Names of private, protected, internal and protected internal fields and properties: **_camelCase**

- Filenames and directory names are **PascalCase**, *e.g.* `MyFile.cs`.

- For casing, a “word” is anything written without internal spaces, including acronyms.  
   *e.g.* `MyRpc instead of MyRPC`.  

> #### Namespaces
- In general, namespaces should be no more than 2 levels deep.
- Don’t force file/folder layout to match namespaces.
- New top-level namespace names must be globally unique and recognizable.

## Brace
- Before opening brace `{`
    1) line break for namespaces, classes, methods, enumerations.
    2) No line break for `if/else`, `for/foreach/while`, `new Object`.

## Whitespace
- Space after commas.
- One space between
    1) a unary operator and its operand.
    2) the operator and each operand of all other operators.
- No space after 
    1) an opening parenthesis or before a closing parenthesis. 
    2) if/for/while etc.
- Line continuations are indented 4 spaces.
- **No** trailing spaces.

***Example***  
```c#
// Bad
using System;
namespace projectName.src.domain.Services {
    public class Projectservice : iProjectService 
    {
        private readonly dBContext DBContext;

        private readonly Ilogger<Projectservice> logger_;

        public Projectservice(dBContext dbcontext,
            Ilogger<Projectservice> logger)
        {
            logger_ = logger;
            DBContext = dbcontext;
        }

        public bool getStatus(bool status) { 
       
            if(status == null)
            {
                throw new ArgumentNullException(
                    nameof(status)
                    )
                }
                }

    } 
}
```
```C#
// Good
using System;

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
        private readonly AtlasDbContext _dbContext;

        /// <summary>
        /// 
        /// </summary>
        private readonly ILogger<ProjectService> _logger;

        /// <summary>
        /// 
        /// </summary>
        public bool status;

        /// <summary>
        /// 
        /// </summary>
        /// <param name="dbContext"></param>
        /// <param name="logger"></param>
        public ProjectService(
            AtlasDbContext dbContext,
            ILogger<ProjectService> logger)
        {
            _logger = logger;
            _dbContext = dbContext;
        }

        /// <summary>
        /// 
        /// </summary>
        /// <returns></returns>
        public bool GetStatus()
        { 
            if(status == null) {
                throw new ArgumentNullException(nameof(status))
            } else {
                // code here...
            }

            return status;
        }
    } 
}
```

# C# coding guidelines

### Using Async 

- All `async` methods must have `Async` suffix.  

***Example***
```c#
// Bad
public async Task<object> MethodName(Options options) 
{
    return null;
}
```
```c#
// Good
public async Task<object> MethodNameAsync(Options options) 
{
    return null;
}
```

### The `var` keyword

- We always use `var` instead of Type to declare a variable.

***Example***
```c#
// Bad
IFormFile file = new IFormFile();
bool fileExists = true;
string file = "test";
```

```c#
// Good
var file = new IFormFile();
var fileExists = true;
var file = "test";
```
