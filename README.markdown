This file is based on https://github.com/raywenderlich/c-sharp-style-guide/blob/master/README.markdown


## Nomenclature

On the whole, naming should follow C# standards.

### Namespaces

Namespaces are all **PascalCase**, multiple words concatenated together, without hyphens ( - ) or underscores ( \_ ). The exception to this rule are acronyms like GUI or HUD, which can be uppercase:

**AVOID**:

```csharp
com.potiongame.game.hud.timer
```

**PREFER**:

```csharp
PotionGame.Game.HUD.Timer
```

### Classes & Interfaces

Classes and interfaces are written in **PascalCase**. For example `RadialSlider`. 

### Methods

Methods are written in **PascalCase**. For example `DoSomething()`. 

### Fields

All non-static fields are written **camelCase**. Per Unity convention, this includes **public fields** as well.

For example:

```csharp
public class MyClass 
{
	public int publicField;
	int packagePrivate;
	private int myPrivate;
	protected int myProtected;
}
```

**AVOID:**

```csharp
private int _myPrivateVariable
```

**PREFER:**

```csharp
private int myPrivateVariable
```

Static fields are the exception and should be written in **PascalCase**:

```csharp
public static int TheAnswer = 42;
```
### Properties

All properties are written in **PascalCase**. For example:

```csharp
public int PageNumber 
{
	get { return pageNumber; }
	set { pageNumber = value; }
}
```

### Parameters

Parameters are written in **camelCase**.

**AVOID:**

```csharp
void DoSomething(Vector3 Location)
```

**PREFER:**

```csharp
void DoSomething(Vector3 location)
```

Single character values are to be avoided except for temporary looping variables.

### Actions

Actions are written in **PascalCase**. For example:

```csharp
public event Action<int> ValueChanged;
```

## Declarations

### Access Level Modifiers

Access level modifiers should be explicitly defined for classes, methods and member variables.

### Fields & Variables

Prefer single declaration per line.

**AVOID:**

```csharp
string username, twitterHandle;
```

**PREFER:**

```csharp
string username;
string twitterHandle;
```

### Classes

Exactly one class per source file, although inner classes are encouraged where scoping appropriate.

### Interfaces

All interfaces should be prefaced with the letter **I**. 

**AVOID:**

```csharp
RadialSlider
```

**PREFER:**

```csharp
IRadialSlider
```

## Spacing

### Indentation

Indentation should be done using **tabs** — never spaces.  

#### Blocks

Indentation for blocks uses **1 tab** for optimal readability:

**AVOID:**

```csharp
for (int i = 0; i < 10; i++) 
{
    Debug.Log("index=" + i);
}
```

**PREFER:**

```csharp
for (int i = 0; i < 10; i++) 
{
	Debug.Log("index=" + i);
}
```

#### Line Wraps

Indentation for line wraps should use **1 tab** (not the default 2):

**AVOID:**

```csharp
CoolUiWidget widget =
		someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

**PREFER:**

```csharp
CoolUiWidget widget =
	someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

### Line Length

Lines should be no longer than **100** characters long.

### Vertical Spacing

There should be exactly one blank line between methods to aid in visual clarity 
and organization. Whitespace within methods should separate functionality, but 
having too many sections in a method often means you should refactor into
several methods.


## Brace Style

Unless it is for a class or struct, opening braces are to be placed in line, closing braces are to be placed on their own line. For classes and structs, both receive their own line

**AVOID:**

```csharp
class MyClass 
{
	void DoSomething() 
	{
		if (someTest) 
		{
			// ...
		} else 
		{
		        // ...
		}
	}
}
```

**PREFER:**

```csharp
class MyClass
{
	void DoSomething(){
		if (someTest){
	          // ...
		}
		else{
		  // ...
		}
	}
}
```

Conditional statements are always required to be enclosed with braces,
irrespective of the number of lines required.

**AVOID:**

```csharp
if (someTest)
    doSomething();  

if (someTest) doSomethingElse();
```

**PREFER:**

```csharp
if (someTest){
	DoSomething();
}  

if (someTest){ DoSomethingElse(); }
```
## Switch Statements

Switch-statements come with `default` case by default. If the `default` case is never reached, be sure to remove it.

**AVOID:**  
  
```csharp
switch (variable) 
{
    case 1:
        break;
    case 2:
        break;
    default:
        break;
}
```

**PREFER:**  
  
```csharp
switch (variable) 
{
    case 1:
        break;
    case 2:
        break;
}
```

## Language

Use US English spelling.

**AVOID:**

```csharp
string colour = "red";
```

**PREFER:**

```csharp
string color = "red";
```

The exception here is `MonoBehaviour` as that's what the class is actually called.
