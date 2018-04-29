# Introduction

## Grails | What is it?

Grails previously known as "Groovy on Rails" is an open source web application framework which uses Apache Groovy programming language.

## Groovy | What is it ?

It's object oriented programming language based on java platform. All the grammer of the language is dervied from Java.
Learn in depth about Groovy from [Groovy Documentation](http://groovy-lang.org/documentation.html). 

## Overview of groovy

Groovy can be downloaded from [link](http://groovy-lang.org/download.html)  

## Starting with groovy 

### Starting with groovy | Installation
`Windows`

1. Download a stable groovy distribution from Offical website of [Apache Groovy](http://groovy-lang.org/download.html).
2. After completing installation add a new environment variable `GROOVY_HOME` targetting the directory where groovy is installed and a new `Path` targetting `GROOVY_HOME\bin` 
3. Go to console and type `groovysh` to bring up a groovy shell or `groovyConsole` to bring up a GUI Swing Interactive Console.

### Let's program a HelloWorld application

Since the following packages are imported by default; you don't have to worry about import statements for this program : 


- java.io.*

- java.lang.*

- java.math.BigDecimal

- java.math.BigInteger

- java.net.*

- java.util.*

- groovy.lang.*

- groovy.util.*

```java
class HelloWorld {
   static void main(String[] args) {
      println('Hello World');
   }
}
```

`Note : Semicolumns are usually optional in groovy`

### Running the above program.

#### From terminal 

1. Go to the directory where you created HelloWorld.groovy file and type `groovyc HelloWorld.groovy` this will compile the file and generate a `HelloWorld.class` file just like in java, or simply type `groovy HelloWorld.groovy` to see the output. 

#### From groovy Swing console

2. Type `groovyConsole` in terminal to bring up a groovy console and write the above program and run to see the output of the file.
*********************
`output : Hello World`

----------------------

### Syntax

For a detailed look into Syntax of groovy [link](http://groovy-lang.org/syntax.html)

1. Comment

`Commenting is just like of java`

```Java
// a standalone single line comment
println "hello" // a comment till the end of the line
```

```Java
/* a standalone multiline comment
   spanning two lines */
println "hello" /* a multiline comment starting
                   at the end of a statement */
println 1 /* one */ + 2 /* two */
```


2. Keywords

||||
|-|-|-|
|as|assert|break|
|case|if|implements|
|import|in|instanceof|
|interface|new|null|
|package|return|super|
|switch|this|throw|throws|
|trait|true|try|while

### Program Structure

1. Package names

```Java
package com.yoursite
```

2. Imports

```Java
// importing the class MarkupBuilder
import groovy.xml.MarkupBuilder
```


3. Scripts in Groovy

3.1 PSVM vs Script

With groovy following both code gives the same output

3.1.1 
```Java
class Main {                                    
    static void main(String... args) {          
        println 'Groovy world!'                 
    }
}
```

3.1.2   
```Java
println 'Groovy world!'
```

##### How is so ?

A script is always compiled into a class. The Groovy compiler will compile the class for you, with the body of the script copied into a run method. The previous example is therefore compiled as if it was the following:

```Java
import org.codehaus.groovy.runtime.InvokerHelper
class Main extends Script {                     
    def run() {                                 
        println 'Groovy world!'                 
    }
    static void main(String[] args) {           
        InvokerHelper.runScript(Main, args)     
    }
}
```