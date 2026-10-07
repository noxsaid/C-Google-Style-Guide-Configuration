# C# Google Style Guide Configuration

This repository contains a `.editorconfig` file that enforces the **Google C# Style Guide** in Visual Studio Code. This ensures consistent code formatting and style across all C# projects.

## 📋 Overview

The `.editorconfig` file automatically applies Google's C# coding standards including:
- 2-space indentation
- 100-character line limit
- PascalCase naming for classes and methods
- camelCase naming for variables and parameters
- _camelCase naming for private fields
- Consistent brace placement and spacing

## 🚀 Quick Start

### Step 1: Add the `.editorconfig` File to Your Project

1. **Download or copy** the `.editorconfig` file from this repository
2. **Place it in the root directory** of your C# project

Your project structure should look like this:

```
MyProject/
├── .editorconfig          ← File goes here (root level)
├── .gitignore
├── README.md
├── bin/
├── obj/
├── src/
│   ├── Program.cs
│   ├── Models/
│   └── Services/
├── MyProject.csproj
└── MyProject.sln
```

### Step 2: Install EditorConfig Extension in VS Code

1. Open **Visual Studio Code**
2. Click on the **Extensions icon** in the left sidebar (or press `Ctrl+Shift+X`)
3. Search for **"EditorConfig"**
4. Install the official **EditorConfig for VS Code** extension by EditorConfig

![Extension Installation](https://img.shields.io/badge/Extension-EditorConfig-blue)

### Step 3: Reload VS Code

After installing the extension:
1. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac)
2. Type **"Reload Window"**
3. Press Enter

### Step 4: Start Coding

The `.editorconfig` file is now active! When you create or edit `.cs` files, the Google C# style rules will automatically apply.

## 📝 What the `.editorconfig` File Contains

### Indentation & Spacing
```
indent_style = space
indent_size = 2      # 2-space indentation (Google standard)
max_line_length = 100
```

### Naming Conventions

| Element | Convention | Example |
|---------|-----------|---------|
| Classes | PascalCase | `public class UserService` |
| Methods | PascalCase | `public void CalculateTotal()` |
| Properties | PascalCase | `public string Name { get; set; }` |
| Local Variables | camelCase | `int totalCount = 0;` |
| Parameters | camelCase | `void Process(int itemCount)` |
| Private Fields | _camelCase | `private string _userName;` |
| Constants | UPPER_SNAKE_CASE | `const int MAX_ATTEMPTS = 5;` |
| Interfaces | IPascalCase | `public interface IRepository` |

### Formatting Rules

**Braces:**
```csharp
// Always use braces, even for single statements
if (condition)
{
    DoSomething();
}
```

**Spacing:**
- Space after keywords: `if (`, `for (`, `while (`
- Space after commas: `Method(param1, param2)`
- No space inside parentheses: `Method(param)` ✓ (not `Method( param )`)
- Space around operators: `int x = 5 + 3;`

**Line Limit:**
- Maximum 100 characters per line (for readability)

## ✅ Verification: How It Should Look

When the `.editorconfig` is properly configured, your code will automatically format like this:

### Example 1: Class Definition
```csharp
namespace MyNamespace
{
  public class UserService
  {
    private string _userId;
    private readonly IRepository _repository;

    public UserService(IRepository repository)
    {
      _repository = repository;
    }

    public User GetUser(int userId)
    {
      var user = _repository.FindById(userId);
      return user;
    }

    private bool ValidateUser(string userName)
    {
      return !string.IsNullOrEmpty(userName);
    }
  }
}
```

### Example 2: Method with Proper Spacing
```csharp
public class Calculator
{
  public int Add(int firstNumber, int secondNumber)
  {
    int result = firstNumber + secondNumber;
    return result;
  }

  public List<int> ProcessNumbers(IEnumerable<int> numbers)
  {
    var validNumbers = numbers
      .Where(n => n > 0)
      .ToList();
    return validNumbers;
  }
}
```

### Example 3: Constants and Fields
```csharp
public class Configuration
{
  private const int MAX_RETRY_COUNT = 3;
  private const string DEFAULT_TIMEOUT = "30s";

  private int _currentRetries;
  private string _connectionString;

  public string ApplicationName { get; set; }
}
```

## 🔍 Troubleshooting

### The `.editorconfig` File Isn't Working

1. **Verify the file is in the project root:**
   - Not in a subfolder
   - Not in the `src/` folder
   - At the same level as `.csproj` or `.sln`

2. **Check that EditorConfig extension is installed:**
   - Go to Extensions (Ctrl+Shift+X)
   - Search "EditorConfig"
   - Ensure it shows "Installed"

3. **Reload VS Code:**
   - Press `Ctrl+Shift+P`
   - Type "Reload Window"
   - Press Enter

4. **Check VS Code settings:**
   - Press `Ctrl+,` to open Settings
   - Search "editorconfig"
   - Ensure "EditorConfig: Enable" is checked ✓

### Formatting Doesn't Apply on Save

1. **Enable format on save:**
   - Press `Ctrl+,` (Settings)
   - Search "format on save"
   - Check "Editor: Format On Save" ✓

2. **Set C# formatter:**
   - Search "C# formatting"
   - Set default formatter to "Omnisharp" or "C#"

## 📦 File Structure for GitHub

When uploading to GitHub, your repository should look like:

```
your-repo/
├── .editorconfig          ← Configuration file
├── .gitignore
├── README.md             ← This file
├── src/
│   ├── Program.cs
│   └── ...
├── tests/
│   └── ...
└── project-name.csproj
```

### Add `.editorconfig` to Git

```bash
git add .editorconfig
git commit -m "Add Google C# Style Guide configuration"
git push origin main
```

## 🎯 For Your Class

When you create your GitHub repo for class:

1. **Copy the `.editorconfig` file** to your project root
2. **Push it to GitHub** with your other project files
3. **Include this README** so classmates know how to set it up
4. **All team members** should:
   - Clone the repo
   - Install the EditorConfig extension
   - Reload VS Code
   - Start coding with automatic formatting! ✅

## 📚 References

- [Google C# Style Guide](https://chromium.googlesource.com/external/github.com/google/styleguide/+/master/csharp-style.md)
- [EditorConfig Documentation](https://editorconfig.org/)
- [EditorConfig VS Code Extension](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

## ⚙️ Customization

If you need to modify any rules in the `.editorconfig` file:

1. Open `.editorconfig` in VS Code
2. Find the rule you want to change
3. Modify the value (e.g., change `indent_size = 2` to `indent_size = 4`)
4. Save the file
5. Reload VS Code

Common settings to customize:
- `indent_size` - Change indentation width
- `max_line_length` - Change line length limit
- Naming rules - Adjust naming conventions
- Severity levels - Change `suggestion` to `warning` or `error`

## 📧 Questions?

If you have questions about the configuration or Google C# Style Guide, refer to the [official documentation](https://chromium.googlesource.com/external/github.com/google/styleguide/+/master/csharp-style.md).

---

**Happy coding!** 🚀
