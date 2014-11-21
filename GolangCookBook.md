Golang Cookbook
===============
> A golang cookbook 

**Convert a string to a float.**
Use the [strconv](http://golang.org/pkg/strconv/#ParseFloat) library's parse functions
```go
import "strconv"
...
strconv.ParseFloat("stringToconvert", 64)
```
**How to determine an interface{} value's “real” type?**
```go
st := arguments["exargs>"]
strconv.ParseFloat(st.(string), 64)
```

