 - [How to Compile and Run Java Code from a Command Line](http://www.sergiy.ca/how-to-compile-and-launch-java-code-from-command-line/)
    - javac asdf.java
    - java -cp . asdf
 - [Error: Could not find or load main class [duplicate]](http://stackoverflow.com/questions/7485670/error-could-not-find-or-load-main-class)
 
 If the class is in a package
 
 package thepackagename;
 
 public class TheClassName {
   public static final void main(String[] cmd_lineParams)  {
      System.out.println("Hello World!");
   } 
 }
 Then calling the following results in Error: Could not find or load main class TheClassName.
 
 java -classpath . TheClassName
 It must be called with its fully-qualified name:
 
 java -classpath . thepackagename.TheClassName
 And this command must be called from the directory in which the thepackagename directory exists.