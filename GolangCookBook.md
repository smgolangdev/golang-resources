Golang Cookbook
===============
> A golang cookbook 

### 1. Convert a string to a float.
Use the [strconv](http://golang.org/pkg/strconv/#ParseFloat) library's parse functions
```go
import "strconv"
...
strconv.ParseFloat("stringToconvert", 64)
```
###2. How to determine an interface{} value's “real” type?
```go
st := arguments["exargs>"]
strconv.ParseFloat(st.(string), 64)
```

###3. How to do an in-place swap?
Use tuples to do an in-place swap. Go supports assigning to a list of variables. When assigning a list of variables to another list the process is split into two steps. In the first step any expressions such as slice indexing or pointer indirections are evaluated in the usual order of precedence. Then the assignments are carried out in left to right order.

```go
 a := 2
 b := 3

a,b = b,a
```
This two step process means that the same technique can be used to exchange values in a slice, for example:
```go
s := []int{2,3}
s[0],s[1] = s[1], s[0]

//Another example with pointers
var a = new(int)
var b = new(int)

*a = 5
*b = 12

*b, *a = *a, *b
```
####See Also
Go Language Specification: [Assignments](http://golang.org/ref/spec#Assignments)

###4. Looping forever
Sometimes one needs to loop forever without doing anything. Most common scenarios are when one waits for **io** or to be interrupted.

instead of using looping constructs such as 
```go
for {}
```
use empty select{}
```go
select {}
```
Empty infinte loops are often used to provide blocking behaviour for part or all of an application. You may be tempted to use an infinite for loop such as: for{} but this is inefficient since it wastes cpu time and cannot be pre-empted by the garbage collector. 

A select with zero cases is optimised by the compiler into a simple blocking statement.

####See Also
[Go Language Specification - select statements](http://golang.org/ref/spec#Select_statements)

###5. Futures in Go
You have a function that returns an error, you want to run it in a goroutine. How to retrieve the error?

**Solution**
One possible solution could be to start a function that returns an error, in a go routine such that it returns a channel from which the error can be read and retrieved. Here is an example from docker's [utils.go](https://github.com/docker/docker/blob/66c8f87e89ba0dd824cf640a159210fbbb8019ec/utils/utils.go#L40) implementation.
```go
	func Go(f func() error) chan error {
		ch := make(chan error, 1)
		go func() {
			ch <- f()
		}()
		return ch
	}
```
####See Also
[Guillaume's post on Go futures.](http://blog.charmes.net/search/label/Golang)

###6. Parsing command line arguments.
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
 
 fmt.Println(arguments) //Prints all the arguments
 //Prints out a named argument from the arguments map
 fmt.Println(arguments["<argumentName>"]) 
 
```
### 7. Files

 1. Reading from a file
 2. Writing to a file
 3. Searching and replacing text in a file
 4. Reading a specific line from a file
 5. Counting number of lines in a file
 6. Processing every word in a file
 7. Using random access input/output
 
### 8. Concurrency

###9. Databases

###10. Sockets

###11. Web 

### Go Present
How to create gopher like presentation slides using **present**?

 1. go get golang.org/x/tools/cmd/present
 2. Write your **.slide** files in [google present format]()
 3. See more example slides [here.](https://github.com/golang/talks/tree/master/2014)
 4. Run $GOPATH/bin/present from the directory containing your .slide files
 5. Point your browser to http://127.0,0,1:3999
 6. 
References

1. Go lang project [examples](https://github.com/golang/example)

 