# go-webserver
Coding exercises for building webservice in go language tutorial from PluralSight

# Course

Pluralsight course 'Go: Getting Started' by Mike Van Sickle

https://app.pluralsight.com/library/courses/f481226c-9b60-4cf5-814c-aa7a125de254/table-of-contents


# Go Commands

## Creating a module

`go mod init github.com/m25lazi/go-webserver`

## Runnning the module

`go run github.com/m25lazi/go-webserver`


# Primitive Data Types

## Declaration

```
	// Variable Declaration
	var i int
	i = 42
	fmt.Println(i)
	
	// You can assign it in the same line
	var pi float32 = 3.14
	fmt.Println(pi)
	
	// Implicit initialization syntax
	name := "Lazim"
	fmt.Println(name)
	
	// You can't use := on name again
	// This fails:
	// name = "Mohammed Lazim"
	name = "Mohammed Lazim"
	fmt.Println(name)
	
	
	// Complex type
	c := complex(3, 4)
	
	// Multiple assignment
	rl, im := real(c), imag(c)
	fmt.Println(rl, im)
```

## Pointers

```
	// Pointer initializer
	var name *string
	fmt.Println(name) // Prints <nil>
	
	// You can't assign like this:
	// name = "Lazim"

	// Using dereferencing operator
	// This will fail since name pointer is not initialised. 
	// *name = "Lazim"
	
	// This is the syntax
	var newname *string = new(string)
	*newname = "Lazim"
	fmt.Println(newname) // Prints memory address
	fmt.Println(*newname) // Prints name
	
	// Go doesn't allow pointer arithmetic
	// *(newname + 1) doesn't work
	
	
	// Address of operator
	firstname := "Lazim"
	fmt.Println(firstname) 
	ptr := &firstname
	
	fmt.Println(ptr, *ptr)
	
	firstname = "Mohammed Lazim"
	fmt.Println(ptr, *ptr)
```

## Constants

```
    // Declaring constants
	const pi = 3.1415
	fmt.Println(pi)
	
	// You cannot re-assign pi again
	// pi = 3.012
	
	// Implicitly interpreted type
	const c = 3
	fmt.Println(c + 3) // Prints 6
	fmt.Println(c + 3.2) // Prints 6.2
	// This works because the c is implecitly interpreted type
	
	const d int = 3
	fmt.Println(d + 3) // Prints 6
	// This doesn't work 
	// fmt.Println(d + 3.2) 
	// But you can use conversion op
	fmt.Println(float32(d) + 3.2) 
```

## IOTA & Constant Expression

```
const pi = 3.1415
const (
	first = 1
	second = "second"
)

/// Notice output changing
const (
	one = iota
	two = iota
)

/// Notice iota resets on constant blocks
const (
	hello = iota + 2
	hi // This takes iota + 2
)

func main() {
	fmt.Println(pi)
	fmt.Println(first, second)
	fmt.Println(one, two) // Prints 0 & 1
	fmt.Println(hello, hi) // Prints 0 + 2 & 1 + 2
	
}
```