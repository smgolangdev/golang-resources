Golang Development
==================
### Go Language Highlights
- Imperative language
- Statically typed
- Syntax similar to Java/C/C++, but less parantheses and no semicolons
- Compiles to native code (no JVM)
- No classes, but structs with methods
- Interfaces
- No implementation inheritance. There's type embedding, though.
- Functions are first class citizens
- Functions can return multiple values
- Go has closures
- Pointers, but not pointer arithmetic
- Built-in concurrency primitives: Goroutines and Channels

###Go Basics
 - **Package Names **
 According to Go's convention the package name is the last element of the import path: the package imported as "crypto/rot13" should be named rot13.
 
 Executable commands must always use package main.

 There is no requirement that package names be unique across all  packages linked into a single binary, only that the import paths (their full file names) be unique.
 
 - **Private and Public methods** - all public methods in a library must begin with Uppercase whereas all private methods should start with a lowercase letter.
 - **Go Functions**

```go
// a simple function
func functionName() {}

// function with parameters (again, types go after identifiers)
func functionName(param1 string, param2 int) {}

// multiple parameters of the same type
func functionName(param1, param2 int) {}

// return type declaration
func functionName() (int) {
    return 42
}
```
- **Functions as Closures and Values**
```go
func main() {
    // assign a function to a name
    add := func(a, b int) int {
        return a + b
    }
    // use the name to call the function
    fmt.Println(add(3, 4))
}

// Closures: Functions can access values that were in scope when defining the
// function

// adder returns an anonymous function with a closure containing the variable sum
func adder() func(int) int {
    sum := 0
    return func(x int) int {
        sum += x // sum is declared outside, but still visible
        return sum
    }
}
```
- **Variadic Functions**
```go
func main() {
    fmt.Println(adder(1, 2, 3)) // return 6
    fmt.Println(adder(9, 9)) // return 18
}

// By using ... before the type name of the last parameter you can indicate that it takes zero or more of those parameters.
// The function is invoked like any other function except we can pass as many arguments as we want.
func adder(args ...int) int {
    total := 0
    for _, v := range args { // Iterates over the arguments whatever the number.
        total += v
    }
    return total
}
```
  
### Development Cookbook
 1. Parsing command line arguments.
 In golang, command line arguments are available via the os package: 
```go
import ( "fmt" "os")

func main() {
   fmt.Println(len(os.Args), Args)
}
```
Another option is to use the **flag** package. It implements command line processing.

However, the best option is to use the [golang implementation](https://github.com/docopt/docopt.go) of Python's classic command line documentation library called [docopt](http://docopt.org/) 

```go
 import ("github.com/docopt/docopt-go")
 
 ...
 fmt.Println(arguments) //Prints all the arguments
 //Prints out a named argument from the arguments map
 fmt.Println(arguments["<argumentName>"]) 
```
###References

 1. [Go by example](https://gobyexample.com/)
 2. [Build You Own Web Framework In Go](http://nicolasmerouze.com/build-web-framework-golang/)
 2. [Beego Web Framework](http://beego.me/)
 3. [Revel web framework]()
 4. Sinatra-style web frameworks. Martini, [Goji](https://github.com/zenazn/goji), [Gin](http://gin-gonic.github.io/gin/) and [gocraft/web](https://github.com/gocraft/web)
 5. [Gorilla web toolkit](http://www.gorillatoolkit.org/)
 6. [Golang Exercises](https://gist.github.com/zyxar/2317744)
 7. [Go Development Setup](http://blog.tideland.biz/2013-07-09-go-environment-setup)
 8. [How to use interfaces in Go](http://jordanorelli.com/post/32665860244/how-to-use-interfaces-in-go)
 9. [Go in a nutshell](https://github.com/basti1302/go-lang-cheat-sheet#go-in-a-nutshell)

