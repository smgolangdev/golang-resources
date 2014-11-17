GoLang Development
===================

####Go Arrays and Slices

An array literal can be specified like so:
```go
 b := [2]string{"Penn", "Teller"}

//Or, you can have the compiler count the array elements for you:

b := [..]string{"Penn", "Teller"}

```

 - Arrays do not need to be initialized explicitly; the zero value of an array is a ready-to-use array whose elements are themselves zeroed:
 - The in-memory representation of [4]int is just four integer values laid out sequentially:
 - Go's arrays are values. An array variable denotes the entire array; it is not a pointer to the first array element (as would be the case in C). This means that when you **assign or pass around an array value you will make a copy of its contents**. (To avoid the copy you could pass a pointer to the array, but then that's a pointer to an array, not an array.)
 -  One way to think about arrays is as a sort of struct but with indexed rather than named fields: a fixed-size composite value.

#### Go Install Notes

 - Use [gvm,](https://github.com/moovweb/gvm) go version manager to install and use multiple versions of go at the same time.
 - gvm does not install godoc therefore install godoc tool by typing in the following
 ```shell
    $ go get -u code.google.com/p/go.tools/cmd/godoc
    #Run the following command to run the go docs locally
    $ godoc -http=:6060  ## point a browser to localhost:6060 to see documentationvb b
    
 ```

####Resources

 1. [Golang source code](https://github.com/jnwhiteh/golang)
 2. [Go package documentation](http://golang.org/pkg/)
 2. [Golang Main Site](http://golang.org/)
 3. [Go for C++ Programmers](GoForCPPProgrammers)
 4. [An Introduction to Programming in Go](http://www.golang-book.com/)
 5. [Don't Get Bitten by Pointer vs Non-Pointer Method Receivers](http://nathanleclaire.com/blog/2014/08/09/dont-get-bitten-by-pointer-vs-non-pointer-method-receivers-in-golang/)
 6. [Deploying Go servers with Docker](http://blog.golang.org/docker)
 7. [Go Slices: usage and internals](http://blog.golang.org/go-slices-usage-and-internals)
 8. [Effective Go](http://golang.org/doc/effective_go.html)
 9. Search for Go packages at [GoDoc](https://godoc.org/)
 10. [Debugging Go code with gdb](https://golang.org/doc/gdb)
 11. [Hopwatch](http://ernestmicklei.com/2012/12/14/hopwatch-a-debugging-tool-for-go/) a debugging tool for Go
 12. [Gopher Go](http://vluxe.io/)