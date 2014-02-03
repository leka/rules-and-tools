# C++ Coding Rules

## Revision History

|Revision	| Author	| Date (dd/mm/yyyy)	| Comment(s)
|:-------------:|:-------------:|:---------------------:|:-------------
| **01**	| mickael@leka	| 15/11/2012		| Document creation
| **02**	| ladislas@leka	| 28/01/2014		| English translation and github push

## Introduction

### Why rules?

This document defines the different coding rules anyone must respect when writing `C++` code at [Leka](http://weareleka.com).

The rules are based upon wildly used standards, several personal experiences, different sources and needs.

There are several reasons for using coding rules:

*  **harmony**: all Leka's projects will follow the same coding rules and styles
*  **readability**: consistency makes the code easier to read
*  **usability**: consistency makes the code easier to use
*  **improvability**: consistency makes the code easier to modify and update
*  **debuggability**: consistency makes the code easier to debug

This document is only here to define the coding style to adopt, it does not contain any technical recommendations.

>So why should one abide by those rules whereas modern IDE already improve readability with syntax coloring, navigation, etc.?

The source code should always be considered outside the development environment and should be written in a way that improves readability in any environment. By doing so, members of the team are allowed to use the tools they prefer for efficient and comfortable coding.

### Rules definitions

Rules are numbered and will be shown as follow:

#### n. Directive

``` C++
Code example if possible.
```

Why/Motivation and additional information.

### Rules hierarchy

In the directive part, verbs like **must**, **should** and **can**, all have specific meanings. A directive with **must**, must be used, a directive with **should**, is highly recommended, and a directive with **can**, is a general directive.

## General Rules

#### 1. Any non-compliance is permitted if it allows for better readability.

``` C++
n/a
```

The main purpose of these rules is to improve readability and thus the understanding, maintainability and the general quality of the code. It is not possible to cover all the specific cases in this document and the developer must be flexible.

## Naming rules

### General naming rules

#### 1. A name representing a `type` must be mixed case and begin with an uppercase letter.

``` C++
SuperClass, Type, Object
```

Common practice in C++ development.

#### 2. A `variable` must be in mixed case and begin with a lowercase letter.

``` C++
variable, myVariable, anotherVariable, ohLookAnotherVariable
```

Common practice in C++ development. Helps the distinction with `type`s and potentially avoids collision when declaring `Object object`.

#### 3. `constant`s and `enumeration`s must be fully uppercase, the words being separated by underscores.

``` C++
CONSTANT, PI, MY_CONSTANT, MY_OTHER_CONSTANT
```

Common practice in C++ development. As a general rule, the use of constants should be minimized. Using a method is better:

``` C++
int getMaxValue() {
   return 10;
}
```

This form is better for unified class interfaces and allows us to implement a method to compute the constant.

#### 4. A name given to a `method` or a `function` must be a verb and be written in mixed case starting with a lowercase letter.

``` C++
getValue(), computeSomething()
```

Common practice in C++ development. Same name as variable but functions are easily distinguishable by their specific form.

#### 5. A name representing a `namespace` must be entirely lowercase.

``` C++
leka::moti, common::data, drivesystem::motors
```

Common practice in C++ development.

#### 6. A name representing a `template` must be a single uppercase letter.

``` C++
template <class T>...
template <class K, class V>...
```

Common practice in C++ development. Template names remain identifiable compared to all other names used.

#### 7. Abbreviations and acronyms should not be uppercase when used as names.

``` C++
exportHtmlSource();
openDvdPlayer();
```

Common practice in C++ development. Using only uppercase letters for the name would be in conflict with Naming Rule [#2](#) and result in strange variable names line `hTML` or `dVD`...

#### 8. `global variable`s must be referenced using the `::` operator.

``` C++
::globalVariable
```

The use of global variables in forbidden. In this case a `singleton pattern` should be considered.

#### 9. In a `class`, a private attribute must be prefixed by and underscore.

``` C++
class MyClass {

   private:

      uint16_t _privateVariable;

}
```

Apart from its `name` and its `type`, the variable's `scope` is important. Using an underscore as a prefix for a private variable helps the distinction from local variables and must therefore be considered with care by the developer.

The underscore also resolve the problem of finding a proper name for setters and constructors:

``` C++
void setDepth(int depth) {
   _depth = depth;:w
}
```

#### 10. A generic variable must have the same name as its type.

``` C++
void setTopic(Topic *topic);
void connect(Database *database);
```

It reduces the complexity by limiting the number of terms and names used. It makes it also easier to identify a variable type thanks to its name. If, for any reason, this rule does not seem to apply well, it's because the name of the type is poorly chosen.

Non-generic variables have a role. They can often be named by combining the role and type:

``` C++
void setTopic(Topic *topic);
Point startingPoint, centerPoint;
Name loginName;
```

#### 11. All names are must be written in English.

``` C++
fileName; // not nomFichier, dateiName, 文件名, etc...
```
English is the language of reference in computer programming.

