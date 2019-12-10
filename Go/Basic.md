# [<span style="color:black;">Go Basic</span>](file:./Go.md)
[Basic](file:./Basic.md) | [Command](file:./Command.md) | [Package](file:./Package.md) | [Example](file:./Example.md)

<br>


## Resource
### General
[golang.org](https://golang.org/) <br>
[github.com](https://github.com/golang/go)<br>
### Tutorial
[godoc.org](https://godoc.org/)<br>
[tour.golang.org](https://tour.golang.org/welcome/1)<br>
[tutorialspoint.com](https://www.tutorialspoint.com/go/index.htm)<br>
[gobyexample.com](https://gobyexample.com/)<br>
[javatpoint.com](https://www.javatpoint.com/go-tutorial)<br>
[medium.com](https://medium.com/rungo)








<br><br><br>
## Install and Config
#### Windows
	download [go1.12.7.windows-amd64.zip] and copy to [C:\Go\core]
	setx PATH %path%;C:\Go\core\bin
	setx GOPATH C:\Go\package 
	setx GOROOT C:\Go\core
	setx GOBIN C:\Go\bin
	setx GOCACHE C:\Go\cache
#### Linux
	cd ~/Downloads/
	wget https://dl.google.com/go/go1.12.7.linux-amd64.tar.gz
	sudo tar -C /usr/local -xzf go1.12.7.linux-amd64.tar.gz	
	mkdir $HOME/go
	echo 'export GOPATH=$HOME/go' >> $HOME/.profile
	echo 'export PATH=$PATH:/usr/local/go/bin' >> $HOME/.profile








<br><br><br>
## Structure

### Compiler

<br>

### Language Specification
> See [Language Specification](https://golang.org/ref/spec)

- Source code representation
- Lexical elements
- Constants
- Variables
- Types
- Properties of types and values
- Blocks
- Declarations and scope
- Expressions
- Statements
- Built-in functions
- Packages
- Program initialization and execution
- Errors
- Run-time panics
- System considerations


<br><br>
### Package
> See [Package Documentation](https://golang.org/pkg/)

#### Standard library
#### Other packages
- Sub-repositories
- Community


<br><br>
### Command
> See [Command Documentation](https://golang.org/doc/cmd)

- go
- cgo
- cover
- fix
- fmt
- godoc
- vet


<br><br>
### Code Organization
#### Executable
#### Package
#### Interfaces
#### .a files libreary


<br><br>
### Concept
##### Concurrency
- Goroutines <br>
- Synchronization <br>
- Channels 

##### Type Casting <br>
##### Recursion <br>
##### Error Handling








<br><br><br>
## Question
<div align="right" dir="rtl">
1اینکه یه فانکش رو کامل بشود ورودی هاشو فهمید 1 <br>
2اینکه در سورس بتوان یک فانکش را بررسی کرد1 <br>
3ساخت یک لایبرری یا پکیج
1
</div>


