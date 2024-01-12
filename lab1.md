# Lab Report 1: Remote Access and File System
## Behavior of Different Terminal Commands
### Behavior of the `cd` Command
   * _No_ Arguments

     ![Image](/cd/noArgument.png)
     * The working directory when the command was run was `/home/lecture1/messages`, as shown in the screenshot
     * By entering the command `cd` with no argument, it runs `cd`'s default action. The user is returned to the root directory, `/home`. 
     * No error occurs.  
   * Path to _Directory_ as Argument

     ![Image](/cd/pathToDirectory.png)
     * The working directory when the command was run was `/home`, as shown in the screenshot
     * By entering the command `cd` followed by the path to a directory, the user is taken to the directory given in the argument, as long as that directory is within the working directory. In this case, since `lecture1` is within the `/home` directory, the user is taken into the `/home/lecture1` directory.
     * No error occurs.
   * Path to _File_ as Argument

     ![Image](/cd/pathToFile.png)
     * The working directory when the command was run was `/home/lecture1`, as shown in the screenshot.
     * An error occurs when this command is run because `cd` is a command that only takes in arguments that are directory paths. Giving it a path to a file results in an error message that states that the file isn't a directory. 
  ---

### Behavior of the `ls` Command
   * _No_ Arguments

     ![Image](/ls/noArgument.png)
     * The working directory when the command was run was `/home`, as shown in the screenshot.
     * When this command is run without any arguments, the contents of the current working directory are listed. In this case, the only thing within the current working directory, `/home`, is the directory `lecture1`, which is exactly what is printed out.
     * No error occurs.  
   * Path to _Directory_ as Argument

     ![Image](/ls/pathToDirectory.png)
     * The working directory when the command was run was `/home`, as shown in the screenshot.
     * When this command is run with an argument that is a path to a directory, the contents of that directory are listed. In this case, the path to the directory `/home/lecture1` is given as an argument and, therefore, the contents of `/home/lecture1` are listed.
     * No error occurs. 
   * Path to _File_ as Argument

     ![Image](/ls/pathToFile.png)
     * The working directory when the command was run was `/home/lecture1`, as shown in the screenshot.
     * When this command is run with an argument that is a path to a file, the name of that file is printed out. In this case, the path for `Hello.java` is passed as an argument, and "Hello.java" is printed out.
     * No error occurs. 
---

### Behavior of the `cat` Command
   * _No_ Arguments

     ![Image](/cat/noArgument.png)
     * The working directory when the command was run was `/home`, as shown in the screenshot.
     * When this command is run with no argument, nothing is initially printed out. However, if you type anything into the command line after the command is run, your input will be printed out. (In the screenshot, I typed in the first "hello". The second "hello" is generated.) This is true until the command is terminated with ctrl-D.
     * No error occurs
   * Path to _Directory_ as Argument

     ![Image](/cat/pathToDirectory.png)
     * The working directory when the command was run was `/home` as shown in the screenshot.
     * When this command is run with a path to a directory as the argument, an error occurs, and the terminal outputs an error message, saying that the argument is a directory. 
   * Path to _File_ as Argument

     ![Image](/cat/pathToFile.png)
     * The working directory when the command was run was `/home/lecture1` as shown in the screenshot.
     * When this command is run with a path to a directory as the argument, each line of the file is printed out. In this case, we use cat on `Hello.java` and, as a result, all the lines of code within `Hello.java` are printed out. 
