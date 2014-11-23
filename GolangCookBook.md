Golang Cookbook
===============
> A golang cookbook 

###Convert a string to a float.
Use the [strconv](http://golang.org/pkg/strconv/#ParseFloat) library's parse functions
```go
import "strconv"
...
strconv.ParseFloat("stringToconvert", 64)
```
###How to determine an interface{} value's “real” type?
```go
st := arguments["exargs>"]
strconv.ParseFloat(st.(string), 64)
```

###How to do an in-place swap?
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

###Looping forever
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

###Futures in Go
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