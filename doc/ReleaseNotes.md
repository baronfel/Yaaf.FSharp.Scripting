### 1.7.2

 * Fix breaking change in FCS

### 1.7.1

 * Fix FAKE Chinese text bug, see https://github.com/matthid/Yaaf.FSharp.Scripting/pull/8

### 1.7.0

 * Add EvalScriptAsInteractionWithOutput and EvalScriptAsInteraction, see https://github.com/Microsoft/visualfsharp/issues/1392

### 1.6.1

 * On CoreCLR we can use the current directory and AppContext.BaseDirectory to resolve assemblies.

### 1.6.0

 * Compatible with dotnet core (netstandard 1.5)
 * Bugfix: 'reportGlobal' wasn't working as intended.
 * Add arguments to `FsiEvaluationException` error message.

### 1.5.2

 * Workaround -g[+|-|:full|:pdbonly] not working as documented.

### 1.5.1

 * Fix forward function not being called with string.Empty if the last line ends with a new-line-character and removeEmptyLines = true (CreateForwardWriter).

### 1.5.0

 * Add a DynamicAssembly and a DynamicAssemblyBuilder property to IFSIEvaluationSession to be able to save the result.

### 1.4.1

 * Use ProgramFilesX86 instead on hard coded value.
 * Minor code improvements.

### 1.4.0

 * ScriptHost is now disposable to be able to dispose the underlying FsiEvaluationSession, fixes https://github.com/matthid/Yaaf.FSharp.Scripting/issues/5

### 1.3.0

 * Use 4.5 reference assemblies in the net45 build.
   You can define NET40 if you include the source and want to continue to use the NET40 reference assemblies.
 * Default to the latest FSharp.Core if possible (but prefer the currently loaded FSharp.Core version)

### 1.2.1

 * Blacklist System.EnterpriseServices.Wrapper as well to fix another warning, see https://github.com/matthid/Yaaf.FSharp.Scripting/issues/4

### 1.2.0

 * Update to latest FSharp.Compiler.Service & FSharp.Core
 * ScriptHost: Change default args to find a FSharp.Core.dll with optdata and sigdata alongside.
 * ScriptHost: Throw early when no FSharp.Core (with sigdata and optdata) can be found when using the default config.

### 1.1.12

 * Ignore System.EnterpriseServices.Thunk.dll, see https://github.com/matthid/Yaaf.FSharp.Scripting/issues/4

﻿### 1.1.11

 * Improve logging output.
 
### 1.1.10

 * Improve logging output.

### 1.1.9

 * Bugfix: Correctly log large argument lists.

### 1.1.8

 * Add logging with System.Diagnostics.TraceSource (configure in app.config with the name "Yaaf.FSharp.Scripting")

### 1.1.7

 * Fix https://github.com/fsharp/FAKE/issues/790 and https://github.com/fsharp/FAKE/issues/794

### 1.1.6

 * Fix https://github.com/fsharp/FAKE/issues/777

### 1.1.5

 * Use case insensitive comparison and compare file-names when manually resolving references

### 1.1.4

 * Fixed a build failure when YAAF_FSHARP_SCRIPTING_PUBLIC is not defined
 * Ignore FSharp.Core.dll in lib-path, when there is no .optdata and .sigdata alongside
 * Don't use a loaded FSharp.Core when it has no .optdata and .sigdata alongside

### 1.1.3

 * Added "Load" to load script files (see https://github.com/matthid/Yaaf.FSharp.Scripting/issues/1)
 * Added "Handle" function to make the usage a bit easier. (see https://github.com/matthid/Yaaf.FSharp.Scripting/issues/2)

### 1.1.2

 * Revert the redirect when using CreateForwardWriter (otherwise users run into unexpected StackOverflowExceptions when printing to stdout or stderr)
   See https://github.com/fsharp/FAKE/pull/771
 * Add an option to remove NewLines when using a forward function (the function will be called whenever a line as been finished)
   Note: You must Dispose the TextWrapper to get the last output (if it wasn't finished with a NewLine character)
 * Add the AppDomain.BaseDirectory to the base path when searching for a FSharp.Core.dll

### 1.1.1

 * Add ScriptHost.CreateForwardWriter which creates a new TextWriter that forwards everything to a simple (string -> unit) function
 * Add session.ChangeCurrentDirectory and session.WithCurrentDirectory, to take care of relative paths within executed snippets
 * Some more docs

### 1.1.0

 * Redirect of stdout and stderr, see https://github.com/fsharp/FSharp.Compiler.Service/issues/201 
 * added an option prevent writing to stdout and stderr

### 1.0.13

 * Introduce FsiEvaluationException when something goes wrong

### 1.0.12

 * Add overloaded methods which return the FSI output and error text
 * Support for running from within FSI.exe

### 1.0.11

 * Add FsiOptions record

### 1.0.10

 * Improve FSharp.Core resolution

### 1.0.9

 * added FSharpAssembly.LoadFiles API

### 1.0.8

 * Support for custom fsi settings object ("fsi")

### 1.0.7

 * Add TryEvalExpression to get the type of the expression (not the runtime type)

### 1.0.6

 * Add support for using the source code files directly (via paket and nuget)

### 1.0.5

 * Add workaround to make scripting work on a clean gentoo install
 * Improve error messages when session creation fails

### 1.0.4

 * Add FSharp.Core nuget package

### 1.0.3

 * Includes a net45 build

### 1.0.2

 * You can now set custom defined symbols

### 1.0.1

 * NuGet dependency FSharp.Compiler.Service added

### 1.0.0

 * Initial release
