<h1 align="center"><img width="500" src="docs/full-logo.png" /></h1>

[![Nuget](https://img.shields.io/nuget/v/faultify.svg?color=blue&label=faultify&style=flat-square)](https://www.nuget.org/packages/faultify/)
[![Nuget](https://img.shields.io/nuget/dt/faultify.svg?style=flat-square)](https://www.nuget.org/packages/faultify/)
![Tester](https://github.com/Faultify/Faultify/workflows/Tester/badge.svg?branch=main)
[![Join us on Discord](https://img.shields.io/discord/801802378721493044.svg?logo=discord)](https://discord.gg/8aKeQFtcnT) 
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=Z8QK6XU749JB2)

## Byte Code Dotnet Mutation Utility
Faultify is a simpel, quick dotnet mutation tool that performs mutations in the byte code to test the test quality of a project. 
Basicly, it imitates the bad programmer by introducing mistakes on purpose. 
A test is supposed to fail after a mutation, if that is not the case the test is probable error-prone.

### Getting Started

- Read the [Technical Book](https://faultify.github.io/Faultify/index.html)
- Benchmark [Statistics](https://github.com/Faultify/Faultify/blob/main/Benchmark/README.md)

**Commandline Options**

```
  -t, --testProjectName    Required. The path pointing to the test project project file.
  
  -r, --reportPath         (Default: ./FaultifyOutput) The path were the report will be saved.
  -f, --reportFormat       (Default: json) Type of report to be generated, options: 'pdf', 'html', 'json'
  -p, --parallel           (Default: 1) Defines how many test sessions are ran at the same time.
  -l, --mutationLevel      (Default: Detailed) The mutation level indicating the test depth.
  
  --help                   Display this help screen.
  --version                Display version information.
```

**Install / Run**

```
dotnet tool install --global faultify --version 0.0.4
faultify -p YourTestProject.csproj -t html
```

The default location for the report is at the executable location in folder '/FaultifyOutput'.

### Features

**Funnctional Features**
- [X] Mutate Arithmetic (+, -, /, *, %) Operators.
- [X] Mutate Assignment Expressions (+=, -=, /=, *=, %=, --, ++).
- [X] Mutate Equivalence Operators (==, !=).
- [X] Mutate Logical Operators (&&, ||).
- [X] Change bitwise operators (^,|, &).
- [X] Mutate Branching statements (if(condition), if(!condition))
- [X] Mutate Variable Literals (true, false).
     - [X] Support for other types.
- [X] Mutate Constant Fields (string, number, boolean).
- [X] Mutate Array initializations (Only arrays larger than 2 elements, all C# types)
- [X] Build mutation report (HTML/PDF).
- [x] Mutation test algorithm.

**Non-Funnctional Features**
- [X] Crossplatform .net core compitability. 
- [X] Nunit/Xunit/Msunit support via `dotnet test`.
- [X] Runnable from console. 

### Solution Projects

| Solution Item | Description |
| :----- | :----- |
| `Faultify.Cli` | `Contains the faultify executable mutation dotnet utility.`|
| `Faultify.Analyze` | `Contains the code that analyzes and searches for mutations`|
| `Faultify.TestRunner` | `Contains the code that runs the mutation test process`|
| `Faultify.Report` | `Contains the code that generates a report`|
| `/Bechmarks` | `Contains a benchmark project and tests that can be used for mutation testing with faultify/stryker.`|


### Alternative
- Source code mutation with mutation switching to speed up compile speed (stryker). 
