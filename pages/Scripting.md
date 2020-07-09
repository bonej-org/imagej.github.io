---
autogenerated: true
title: Scripting
breadcrumb: Scripting
layout: page
author: test author
categories: Scripting
description: test description
---

{% include learn content='scripting' %} ImageJ allows you to write
scripts in several different languages.

# Getting started

  - Read the [ImageJ tutorial
    notebooks](https://imagej.github.io/tutorials) to learn how to write
    ImageJ scripts.
  - Press the

{% include key content='\[' %}

`key to open the `[`Script`` 
 ``Editor`](Script_Editor "wikilink")` (or `

{% include key content='Shift' %} - {% include key content='\[' %}

`to open the `[`Script`` 
 ``Interpreter`](Script_Interpreter "wikilink")`).`

  - Optionally, choose a template from the *Templates* menu to get you
    started.
  - Otherwise, choose your language from the *Language* menu.
  - Grab code snippets for common tasks from the [Scripting
    toolbox](Scripting_toolbox "wikilink").
  - See [Scripting comparisons](Scripting_comparisons "wikilink") for a
    side-by-side comparison of scripting languages.
  - See [:Category:Scripting](:Category:Scripting "wikilink") for a list
    of all scripting-related pages on this wiki.

# Supported languages

ImageJ's [Script Editor](Script_Editor "wikilink") supports many
different languages. The following table summarizes the possibilities.

|                                                                |
| -------------------------------------------------------------- |
| Recommended options                                            |
| [Groovy](Groovy_Scripting "wikilink")                          |
| [ImageJ Macro](Introduction_into_Macro_Programming "wikilink") |
| [Python (Jython)](Jython_Scripting "wikilink")                 |
| [JavaScript](Javascript_Scripting "wikilink")                  |
| [Ruby (JRuby)](JRuby_Scripting "wikilink")                     |
| [Lisp (Clojure)](Clojure_Scripting "wikilink")                 |
| [R (Renjin)](Renjin_Scripting "wikilink")                      |
| Other options                                                  |
| [Java](Java "wikilink")                                        |
| [MATLAB](MATLAB_Scripting "wikilink")                          |
| [BeanShell](Beanshell_Scripting "wikilink")                    |
| [Scala](Scala_Scripting "wikilink")                            |

# Script parameters

There is a universal `@parameter` notation available across all scripts
for declaring inputs and outputs. This approach is preferred to using
ImageJ 1.x `GenericDialog` because it is totally agnostic to the user
interface, allowing such scripts to run in a variety of contexts.

See the [script parameters](script_parameters "wikilink") page for
details.

# Using an interpreter

All scripting languages use the same basic interpreter, with the
following common features.

## General key bindings

  - 
{% include key content='up' %}

  -   
    bring the previously typed command.

<!-- end list -->

  - 
{% include key content='down' %}

  -   
    bring the next typed command.

<!-- end list -->

  - 
{% include key content='enter' %}

`or `

{% include key content='return' %}

  -   
    execute the contents of the prompt.

## Multiline editing and keybindings

You can enlarge the prompt by dragging the middle bar.

  - 
{% include key content='Shift||Enter' %}

  -   
    create a new line within the prompt.

<!-- end list -->

  - 
{% include key content='Shift||Up' %}

  -   
    move to the line above within the prompt.

<!-- end list -->

  - 
{% include key content='Shift|Down' %}

  -   
    move to the line below within the prompt.

## Selecting and executing text from the screen

On selecting text, a popup offers to:

  - copy
  - execute
  - save to a new file

# Using the script editor

You can create, edit and run scripts using the built-in [Script
Editor](Script_Editor "wikilink"). For details, please see [the Script
Editor documentation](Using_the_Script_Editor "wikilink").

# Adding scripts to the Plugins menu

For the script to appear in the ImageJ menus, the following must apply:

1.  The script file is saved in the `ImageJ.app/scripts` or the
    `ImageJ.app/plugins/Scripts` directory (or a subdirectory thereof).
2.  The script name ends in a supported script extension. For example
      - ".groovy" for groovy,
      - ".js" for javascript,
      - ".py" for jython,
      - ".rb" for jruby,
      - ".clj" for clojure,
      - ".bsh" for beanshell, and
      - ".ijm" for ImageJ 1.x macros.
3.  The script name contains a '\_' (underscore) character, e.g.
    "MyScript\_.ijm".

{% capture includecontent %} Replace `ImageJ.app` with `Fiji.app` {%
endcapture %}

{% include fiji content=includecontent %}

The extension will be stripped and any underscores will be turned into
spaces before the script is added to the menus.

Scripts in the top-level `ImageJ.app/plugins` directory will appear at
the bottom of the *Plugins* menu. Scripts can be placed in other menus
by nesting subdirectories, for example placing a script in the
`ImageJ.app/scripts/File` directory will add it to the *File* menu.

If you aren't able to find your script, you can always run the [Command
Finder](Using_the_Command_Launcher "wikilink") to verify its location
(or absence).

Commands added to the menu in the described way can be called from other
scripts. Use the [macro recorder](macro_recorder "wikilink") to get the
required code for doing so.

## Adding JAR-packaged scripts to the menu

Scripts can be packaged in a JAR file for easier distribution to your
colleagues and via \[Update Sites\]. For this purpose,
[example-script-collection](https://github.com/imagej/example-script-collection)
can be used as the template Maven project.

Inside the example-script-collection jar, the scripts are in
`./resources/scripts.` and therefore get added to the menu when the JAR
is on the classpath (i.e. in `./plugins/` or `./jars/`).

ImageJ2 (and therefore Fiji) looks for scripts in subfolders of
`./scripts/` as it is already described in the previous section, and for
jars in `./jars/`. ImageJ1 recognizes plugins and scripts in
`./plugins/`

# Calling a script from another script

There are different ways to call a script from another script.  
Generally, the called script is executed in the same thread than the
calling script, which means that the calling script will wait that the
called script terminates before going on with the rest of the execution.

## Using ImageJ1 commands

ImageJ offers the possibility to call a plugin, macro or script within
another one.  
If the plugin is already part of the Menu, the simple command
`run(PluginName, string Arguments)` (or `IJ.run` for other scripting
languages) as returned by the macro-recorder will work.

However when one wants to call a home-made local macro that is not part
of the ImageJ menu, one uses a different command (see below).  
Here the example of a mainMacro calling a subMacro.

\- mainMacro

``` java
IJ.log("Hello world, I'm mainMacro");
runMacro("C:/structure/temp/subMacro.ijm");
```

\- subMacro

``` java
IJ.log("Hello world, I'm subMacro");
```

It is also possible to pass arguments to the subMacro, it works similar
to the command line execution.  
The subMacro needs to use `getArgument()` (or `IJ.imageJ.getArgs` of the
ImageJ API) to recover the string of argument passed to it.

\- mainMacro

``` java
IJ.log("Hello world, I'm mainMacro");
runMacro("C:/structure/temp/subMacro.ijm", "Arg1,Arg2");
```

\- subMacro

``` java
Arguments = getArgument()
IJ.log(Arguments);
```

The command `runMacro` works only for ijm macro.  
To call a script written in another scripting languages, one should use
the `runMacroFile(PathToScript, Arguments)` (respectively
`IJ.runMacroFile` of the ImageJ API). Still using the `getArgument` to
pass the variables from mainScript to subScript.

This 1st option is however limited to ImageJ1 code style, meaning that
one cannot use script parameters, or call any service in subScript.  
Luckily ImageJ2 also have is own way to call a script within a script.

## Using ImageJ2 command

One can use the ScriptService from scijava to run a script within a
script.  
Here the example of a mainScript calling a subScript both in Jython.

\- mainScript.py

``` python
#@ ScriptService scriptService
from ij import IJ

IJ.log("Hello world, I'm mainScript");
Arguments = ["some_string", "val1", "some_int", 5]
scriptService.run(r"SomePath/subScript.py", True, Arguments);
```

\- subScript.py

``` python
#@ String (label="some_string") some_string
#@ Integer (label="some_int") some_int
IJ.log(some_string)
IJ.log(str(some_int))
```

subScript must use \#@ Script Parameters for the inputs, and mainScript
pass the arguments to subScript as a list of `field, value`

# Running scripts in headless mode

See the [Scripting Headless](Scripting_Headless "wikilink") page for
instructions on executing scripts headlessly.

[Category:Scripting](Category:Scripting "wikilink")