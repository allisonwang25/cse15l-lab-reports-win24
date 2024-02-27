# Lab Report #4: Vim
```
  ssh alw036@ieng6.ucsd.edu <enter>
  git clone git@github.com:allisonwang25/lab7.git <enter>
  cd lab7/ <enter>
  <Ctrl-r> javac <enter>
  <Ctrl-r> java<space> <enter>
  vim ListExamples.java <enter>
  43j e s 2 <escape> :wq
  <Ctrl-r> javac <enter>
  <Ctrl-r> java<space> <enter>
  <Ctrl-r> git<space>c <enter>
  <Ctrl-r> git<space>p <enter>
  ```
* **ssh alw036@ieng6.ucsd.edu** : log in to virtual machine
* **git clone** : clones github repository using ssh key
* **cd** : changes current directory to lab7, the directory with all the files
* **\<Ctrl-r\>** : access bash history and search the characters given after
  * when inputed with "javac", the result that comes up is `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` which compiles all java files
  * when inputed with "java ", the result that comes up is `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` which runs the java file ListExamplesTests
  * when inputed with "git c", the result that comes up is `git commit -m "first commit"` which records changes to the local repository
  * when inputed with "git p", the result that comes up is ` git push -u git@github.com:allisonwang25/lab7.git` which pushes chagnes to the main branch, sending the local repo to Github
* **vim** : open vim editor for the command-line argument afterwords
* **43j** : execute j command which moves cursor down 43 times
* **e** : move to end of next word
* **s** : delete and replace character cursor is on
* **\<escape\>** : exits from editing mode of vim
* **:wq:** : save and quit vim editor
