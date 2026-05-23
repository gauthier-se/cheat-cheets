# Java

## JDK Commands

| Command | Description |
| :--- | :--- |
| `javac <file.java>` | Compile a Java source file into `.class` bytecode |
| `java <ClassName>` | Run a compiled Java class |
| `java -jar <file.jar>` | Execute a packaged JAR file |
| `javap -c <ClassName>` | Disassemble a class file to see the bytecode |
| `jshell` | Launch the interactive Java REPL (Read-Eval-Print Loop) |

## Environment

| Command | Description |
| :--- | :--- |
| `java -version` | Display the installed JRE/JDK version |
| `javac -version` | Display the installed Java compiler version |
| `echo $JAVA_HOME` | Check the path to your JDK installation (on Unix) |

## Quick Execution (Java 11+)

Since Java 11, you can execute a single-file source code without explicitly compiling it first.

```bash
# Simply run the source file directly!
java HelloWorld.java
```
