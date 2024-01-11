# Lab Report 1: Remote Access and File System
## Behavior of Different Terminal Commands
### Behavior of the `cd` Command
   * _No_ Arguments

     ![Image](/cd/noArgument.png)
     * The working directory when the command was run was `/home/lecture1/messages`, as shown in the screenshot
     * By entering the command `cd` with no argument, it runs `cd`'s default action. The user is returned to the root directory, `/home`. 
     * The output is not an error.  
   * Path to _Directory_ as Argument

     ![Image](/cd/pathToDirectory.png)
     * The working directory when the command was run was `/home`, as shown in the screenshot
     * By entering the command `cd` followed by the path to a directory, the user is taken to the directory given in the argument, as long as that directory is within the working directory. In this case, since `lecture1` is within the `/home` directory, the user is taken into the `/home/lecture1` directory.
     * The output is not an error.
   * Path to _File_ as Argument

     ![Image](/cd/pathToFile.png)
     * The working directory when the command was run was `/home/lecture1`, as shown in the screenshot.
     * An error occurs when this command is run because `cd` is a command that only takes in arguments that are directory paths. Giving it a path to a file results in an error message that states that the file isn't a directory. 
---
### Behavior of the `ls` Command
   * _No_ Arguments
   * Path to _Directory_ as Argument
   * Path to _File_ as Argument
---
### Behavior of the `cat` Command
   * _No_ Arguments
   * Path to _Directory_ as Argument
   * Path to _File_ as Argument
