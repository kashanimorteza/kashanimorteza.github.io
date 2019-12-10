# [<span style="color:black;">Go Example</span>](file:./Go.md)
[Basic](file:./Basic.md) | [Command](file:./Command.md) | [Package](file:./Package.md) | [Example](file:./Example.md)

<br>


## General
#### Run program with parameters
	package main

	import "os"
	import "fmt"

	func main() {

		argsWithProg := os.Args
		argsWithoutProg := os.Args[1:]
		arg := os.Args[1]

		fmt.Println("--------Start----------------")
		fmt.Println(argsWithProg)
		fmt.Println("------------------------")
		fmt.Println(argsWithoutProg)
		fmt.Println("------------------------")
		fmt.Println(arg)
		fmt.Println("--------End----------------")
	}


<br><br>
## File
#### Read from text file
	package main

	import (
		"fmt"
		"io/ioutil"
	)

	func main() {
		
		fmt.Printf("\n-------------- Read from file ------------\n\n")

		data, err := ioutil.ReadFile("text.txt")

		if err != nil {
			fmt.Println("File reading error", err)
			return
		}


		fmt.Printf("data:%v\n", data)
		fmt.Printf("err:%v\n", err)
		fmt.Printf("------------\n")
		fmt.Printf("data type:%T\n", data)
		fmt.Printf("err type:%T\n", err)
		fmt.Printf("------------\n")
		fmt.Printf(string(data))
	}
### Write text file
	package main

	import (
		"fmt"
		"io/ioutil"
	)

	func main() {

		fmt.Printf("\n-------------- Write to file ------------\n\n")

		message := []byte("salam man morteza kashani hastam")

		err := ioutil.WriteFile("text.txt", message, 0644)

		if err != nil {
			fmt.Println("File reading error", err)
			return
		}
	}


<br><br>
## String
#### Split string
	package main

	import (
		"fmt"
		"strings"
	)

	func main() {

		fmt.Printf("\n-------------- Split string ------------\n\n")
		
		s := "salam man morteza kashani hastam"
		ss := strings.Split(s, " ")


		fmt.Printf("string: %v\n", s)
		fmt.Printf("after split: %v\n", ss)
		fmt.Printf("------------\n")
		fmt.Printf("split type: %T\n", ss)
		fmt.Printf("------------\n")
		fmt.Printf("item 0: %v\n", ss[0])
	}
### Remove same 
	package main

	import (
		"fmt"
		"strings"
	)

	func main() {

		fmt.Printf("\n-------------- Remove same ------------\n\n")
		
		s := "salam man morteza kashani hastam salam man morteza kashani hastam salam man morteza kashani hastam"
		ss := strings.Split(s, " ")
		var sss []string
		exist := false

		for i := 0; i < len(ss); i++ {
			exist = false
			for j := 0; j < len(sss); j++ {
				if ss[i] == sss[j] {
					exist = true
					break
				}
			}
			if !exist {
				sss = append(sss, ss[i])
			}
		}


		fmt.Printf("%v\n", ss)
		fmt.Printf("%v\n", sss)
	}
### Read & Split & Remove same & Write
	package main

	import (
		"fmt"
		"io/ioutil"
		"regexp"
		"strings"
	)

	func main() {

		//Header
		fmt.Printf("\n-------------- Read & Split & Remove same & Write ------------\n\n")
		//Read file
		file1, _ := ioutil.ReadFile("1.txt")
		s := string(file1)
		//Remove new line
		re := regexp.MustCompile("\r?\n")
		s = re.ReplaceAllString(s, " ")
		//Split & Remove same
		ss := strings.Split(s, " ")
		var sss []string
		exist := false
		for i := 0; i < len(ss); i++ {
			exist = false
			for j := 0; j < len(sss); j++ {
				if ss[i] == sss[j] {
					exist = true
					break
				}
			}
			if !exist {
				sss = append(sss, ss[i])
			}
		}
		//Convert sss[i] to string
		file2 := strings.Join(sss, " - ")
		//Write to file
		message := []byte(file2)
		_ = ioutil.WriteFile("2.txt", message, 0644)
		//Print
		fmt.Printf("%v\n", string(file2))
	}
