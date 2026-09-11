# 🐹 Go (Golang) — Beginner to Advanced

> A complete Go programming guide from **Beginner → Intermediate → Advanced**, with practical examples, explanations in **English + Khmer**, and runnable code.

---

## 📚 Table of Contents

* [1. What is Go?](#1-what-is-go)
* [2. Installation](#2-installation)
* [3. Your First Go Program](#3-your-first-go-program)
* [4. Program Structure](#4-program-structure)
* [5. Variables](#5-variables)
* [6. Constants](#6-constants)
* [7. Data Types](#7-data-types)
* [8. Type Conversion](#8-type-conversion)
* [9. Operators](#9-operators)
* [10. Input and Output](#10-input-and-output)
* [11. Conditions](#11-conditions)
* [12. Switch](#12-switch)
* [13. Loops](#13-loops)
* [14. Functions](#14-functions)
* [15. Multiple Return Values](#15-multiple-return-values)
* [16. Variadic Functions](#16-variadic-functions)
* [17. Defer](#17-defer)
* [18. Arrays](#18-arrays)
* [19. Slices](#19-slices)
* [20. Maps](#20-maps)
* [21. Strings](#21-strings)
* [22. Pointers](#22-pointers)
* [23. Structs](#23-structs)
* [24. Methods](#24-methods)
* [25. Interfaces](#25-interfaces)
* [26. Embedding](#26-embedding)
* [27. Error Handling](#27-error-handling)
* [28. Custom Errors](#28-custom-errors)
* [29. Packages](#29-packages)
* [30. Go Modules](#30-go-modules)
* [31. Goroutines](#31-goroutines)
* [32. Channels](#32-channels)
* [33. Buffered Channels](#33-buffered-channels)
* [34. Select](#34-select)
* [35. WaitGroup](#35-waitgroup)
* [36. Mutex](#36-mutex)
* [37. Context](#37-context)
* [38. Generics](#38-generics)
* [39. Reflection](#39-reflection)
* [40. JSON](#40-json)
* [41. File Handling](#41-file-handling)
* [42. HTTP Server](#42-http-server)
* [43. HTTP Client](#43-http-client)
* [44. REST API](#44-rest-api)
* [45. Middleware](#45-middleware)
* [46. Testing](#46-testing)
* [47. Benchmarks](#47-benchmarks)
* [48. Dependency Injection](#48-dependency-injection)
* [49. Clean Project Structure](#49-clean-project-structure)
* [50. Advanced Concurrency](#50-advanced-concurrency)
* [51. Best Practices](#51-best-practices)
* [52. Learning Roadmap](#52-learning-roadmap)

---

# 1. What is Go?

## English

**Go**, also called **Golang**, is an open-source programming language designed for simplicity, performance, concurrency, and reliable software development.

Go is commonly used for:

* Backend development
* REST APIs
* Microservices
* Cloud applications
* DevOps tools
* Networking
* CLI applications
* Distributed systems
* High-performance servers

## ខ្មែរ

**Go (Golang)** គឺជាភាសាកម្មវិធីដែលផ្តោតលើ៖

* ភាពងាយស្រួលក្នុងការសរសេរ
* Performance ខ្ពស់
* Concurrency
* Backend/API
* Cloud និង Microservices
* Networking
* DevOps

---

# 2. Installation

Check whether Go is installed:

```bash
go version
```

Create a project:

```bash
mkdir hello-go
cd hello-go
```

Initialize a Go module:

```bash
go mod init example.com/hello-go
```

Run your program:

```bash
go run .
```

Build:

```bash
go build
```

Format code:

```bash
gofmt -w .
```

## ខ្មែរ

`go mod init` ប្រើសម្រាប់បង្កើត **Go Module**។

`go run .` ប្រើសម្រាប់ run project។

`go build` ប្រើសម្រាប់ compile project។

`gofmt` ប្រើសម្រាប់ format Go code ឱ្យមានស្តង់ដារ។

---

# 3. Your First Go Program

Create:

```text
main.go
```

Full code:

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello, World!")
}
```

Run:

```bash
go run main.go
```

Output:

```text
Hello, World!
```

## Explanation

```go
package main
```

The program belongs to the `main` package.

```go
import "fmt"
```

Imports the `fmt` package.

```go
func main()
```

The `main()` function is the entry point of an executable Go program.

```go
fmt.Println(...)
```

Prints text to the terminal.

## ខ្មែរ

* `package main` → package សម្រាប់ executable program
* `import "fmt"` → នាំចូល package `fmt`
* `func main()` → function ដែល program ចាប់ផ្តើមពីទីនេះ
* `fmt.Println()` → បង្ហាញអត្ថបទទៅ terminal

---

# 4. Program Structure

A basic Go program looks like:

```go
package main

import "fmt"

func main() {
	fmt.Println("Go Programming")
}
```

General structure:

```text
Package
   ↓
Imports
   ↓
Functions
   ↓
Program execution
```

---

# 5. Variables

## Using `var`

```go
package main

import "fmt"

func main() {
	var name string = "Dara"
	var age int = 20

	fmt.Println(name)
	fmt.Println(age)
}
```

## Type inference

```go
package main

import "fmt"

func main() {
	var name = "Dara"
	var age = 20

	fmt.Println(name)
	fmt.Println(age)
}
```

## Short declaration

```go
package main

import "fmt"

func main() {
	name := "Dara"
	age := 20

	fmt.Println(name, age)
}
```

## Multiple variables

```go
package main

import "fmt"

func main() {
	name, age := "Dara", 20

	fmt.Println(name)
	fmt.Println(age)
}
```

## ខ្មែរ

`:=` គឺជា **short variable declaration**។

```go
name := "Dara"
```

Go នឹងស្គាល់ type ដោយស្វ័យប្រវត្តិថា `string`។

---

# 6. Constants

Constants cannot be changed after declaration.

```go
package main

import "fmt"

const Pi = 3.14159

func main() {
	fmt.Println(Pi)
}
```

Another example:

```go
package main

import "fmt"

const (
	AppName = "My Go App"
	Version = "1.0.0"
)

func main() {
	fmt.Println(AppName)
	fmt.Println(Version)
}
```

## ខ្មែរ

`const` ប្រើសម្រាប់តម្លៃដែលយើងមិនចង់ឱ្យផ្លាស់ប្តូរ។

---

# 7. Data Types

Go has several important types.

## Integer

```go
var age int = 20
```

## Floating point

```go
var price float64 = 19.99
```

## Boolean

```go
var isActive bool = true
```

## String

```go
var name string = "Dara"
```

## Complex

```go
var number complex128 = 1 + 2i
```

Example:

```go
package main

import "fmt"

func main() {
	var age int = 20
	var price float64 = 19.99
	var active bool = true
	var name string = "Dara"

	fmt.Println(age)
	fmt.Println(price)
	fmt.Println(active)
	fmt.Println(name)
}
```

---

# 8. Type Conversion

Go does not automatically convert numeric types.

```go
package main

import "fmt"

func main() {
	var age int = 20

	var price float64 = float64(age)

	fmt.Println(price)
}
```

String conversion:

```go
package main

import (
	"fmt"
	"strconv"
)

func main() {
	number := 100

	text := strconv.Itoa(number)

	fmt.Println(text)
}
```

String to integer:

```go
package main

import (
	"fmt"
	"strconv"
)

func main() {
	text := "100"

	number, err := strconv.Atoi(text)

	if err != nil {
		fmt.Println("Invalid number")
		return
	}

	fmt.Println(number)
}
```

## ខ្មែរ

Go ត្រូវការ conversion ដោយ explicit។

ឧទាហរណ៍៖

```go
float64(age)
```

មានន័យថា convert `int` ទៅ `float64`។

---

# 9. Operators

## Arithmetic

```go
package main

import "fmt"

func main() {
	a := 10
	b := 3

	fmt.Println(a + b)
	fmt.Println(a - b)
	fmt.Println(a * b)
	fmt.Println(a / b)
	fmt.Println(a % b)
}
```

## Comparison

```go
package main

import "fmt"

func main() {
	a := 10
	b := 20

	fmt.Println(a == b)
	fmt.Println(a != b)
	fmt.Println(a > b)
	fmt.Println(a < b)
	fmt.Println(a >= b)
	fmt.Println(a <= b)
}
```

## Logical

```go
package main

import "fmt"

func main() {
	age := 20
	active := true

	fmt.Println(age >= 18 && active)
	fmt.Println(age >= 18 || active)
	fmt.Println(!active)
}
```

---

# 10. Input and Output

Using `fmt.Scanln`:

```go
package main

import "fmt"

func main() {
	var name string

	fmt.Print("Enter your name: ")
	fmt.Scanln(&name)

	fmt.Println("Hello,", name)
}
```

Multiple values:

```go
package main

import "fmt"

func main() {
	var name string
	var age int

	fmt.Print("Enter name and age: ")
	fmt.Scan(&name, &age)

	fmt.Println("Name:", name)
	fmt.Println("Age:", age)
}
```

## ខ្មែរ

`&name` មានន័យថាយក **memory address** របស់ variable `name` ដើម្បីឱ្យ `Scan` អាចដាក់តម្លៃចូល variable បាន។

---

# 11. Conditions

## if

```go
package main

import "fmt"

func main() {
	age := 20

	if age >= 18 {
		fmt.Println("Adult")
	}
}
```

## if / else

```go
package main

import "fmt"

func main() {
	age := 16

	if age >= 18 {
		fmt.Println("Adult")
	} else {
		fmt.Println("Minor")
	}
}
```

## else if

```go
package main

import "fmt"

func main() {
	score := 85

	if score >= 90 {
		fmt.Println("A")
	} else if score >= 80 {
		fmt.Println("B")
	} else if score >= 70 {
		fmt.Println("C")
	} else {
		fmt.Println("Fail")
	}
}
```

---

# 12. Switch

```go
package main

import "fmt"

func main() {
	day := 2

	switch day {
	case 1:
		fmt.Println("Monday")
	case 2:
		fmt.Println("Tuesday")
	case 3:
		fmt.Println("Wednesday")
	default:
		fmt.Println("Unknown day")
	}
}
```

Multiple conditions:

```go
package main

import "fmt"

func main() {
	day := "Saturday"

	switch day {
	case "Saturday", "Sunday":
		fmt.Println("Weekend")
	default:
		fmt.Println("Weekday")
	}
}
```

---

# 13. Loops

Go has one main looping keyword:

```go
for
```

## Basic loop

```go
package main

import "fmt"

func main() {
	for i := 0; i < 5; i++ {
		fmt.Println(i)
	}
}
```

## While-style loop

```go
package main

import "fmt"

func main() {
	i := 0

	for i < 5 {
		fmt.Println(i)
		i++
	}
}
```

## Infinite loop

```go
package main

import "fmt"

func main() {
	for {
		fmt.Println("Running...")
		break
	}
}
```

## Continue

```go
package main

import "fmt"

func main() {
	for i := 0; i < 10; i++ {
		if i%2 == 0 {
			continue
		}

		fmt.Println(i)
	}
}
```

## ខ្មែរ

Go មិនមាន `while` keyword ទេ។

យើងប្រើ:

```go
for condition {
}
```

ជំនួស `while`។

---

# 14. Functions

Basic function:

```go
package main

import "fmt"

func greet() {
	fmt.Println("Hello!")
}

func main() {
	greet()
}
```

Function parameters:

```go
package main

import "fmt"

func greet(name string) {
	fmt.Println("Hello,", name)
}

func main() {
	greet("Dara")
}
```

Return value:

```go
package main

import "fmt"

func add(a int, b int) int {
	return a + b
}

func main() {
	result := add(10, 20)

	fmt.Println(result)
}
```

Short parameter syntax:

```go
func add(a, b int) int {
	return a + b
}
```

---

# 15. Multiple Return Values

One of Go's important features is multiple return values.

```go
package main

import "fmt"

func divide(a, b float64) (float64, error) {
	if b == 0 {
		return 0, fmt.Errorf("cannot divide by zero")
	}

	return a / b, nil
}

func main() {
	result, err := divide(10, 2)

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println("Result:", result)
}
```

## ខ្មែរ

Go អនុញ្ញាតឱ្យ function return តម្លៃច្រើន។

```go
(value, error)
```

នេះមានប្រយោជន៍ខ្លាំងសម្រាប់ error handling។

---

# 16. Variadic Functions

A variadic function accepts any number of arguments.

```go
package main

import "fmt"

func sum(numbers ...int) int {
	total := 0

	for _, number := range numbers {
		total += number
	}

	return total
}

func main() {
	fmt.Println(sum(1, 2, 3))
	fmt.Println(sum(10, 20, 30, 40))
}
```

The `...int` means:

```text
0 or more int values
```

---

# 17. Defer

`defer` delays a function call until the surrounding function returns.

```go
package main

import "fmt"

func main() {
	defer fmt.Println("Third")
	fmt.Println("First")
	fmt.Println("Second")
}
```

Output:

```text
First
Second
Third
```

Multiple defer calls execute in **LIFO** order.

```go
package main

import "fmt"

func main() {
	defer fmt.Println("A")
	defer fmt.Println("B")
	defer fmt.Println("C")

	fmt.Println("Main")
}
```

Output:

```text
Main
C
B
A
```

---

# 18. Arrays

An array has a fixed length.

```go
package main

import "fmt"

func main() {
	var numbers [5]int

	numbers[0] = 10
	numbers[1] = 20

	fmt.Println(numbers)
}
```

Initialize:

```go
package main

import "fmt"

func main() {
	numbers := [5]int{10, 20, 30, 40, 50}

	fmt.Println(numbers)
}
```

Iterate:

```go
package main

import "fmt"

func main() {
	numbers := [5]int{10, 20, 30, 40, 50}

	for index, value := range numbers {
		fmt.Println(index, value)
	}
}
```

---

# 19. Slices

Slices are dynamic and commonly used instead of arrays.

```go
package main

import "fmt"

func main() {
	numbers := []int{10, 20, 30}

	fmt.Println(numbers)

	numbers = append(numbers, 40)

	fmt.Println(numbers)
}
```

Length:

```go
len(numbers)
```

Capacity:

```go
cap(numbers)
```

Slice example:

```go
package main

import "fmt"

func main() {
	numbers := []int{10, 20, 30, 40, 50}

	part := numbers[1:4]

	fmt.Println(part)
}
```

Output:

```text
[20 30 40]
```

---

# 20. Maps

A map stores key-value pairs.

```go
package main

import "fmt"

func main() {
	ages := map[string]int{
		"Dara": 20,
		"Sok":  25,
	}

	fmt.Println(ages["Dara"])
}
```

Add:

```go
ages["Chan"] = 30
```

Delete:

```go
delete(ages, "Sok")
```

Check key:

```go
package main

import "fmt"

func main() {
	ages := map[string]int{
		"Dara": 20,
	}

	age, exists := ages["Dara"]

	if exists {
		fmt.Println("Age:", age)
	} else {
		fmt.Println("User not found")
	}
}
```

---

# 21. Strings

Basic string:

```go
package main

import "fmt"

func main() {
	message := "Hello Go"

	fmt.Println(message)
	fmt.Println(len(message))
}
```

String operations:

```go
package main

import (
	"fmt"
	"strings"
)

func main() {
	text := "Hello Go Programming"

	fmt.Println(strings.ToUpper(text))
	fmt.Println(strings.ToLower(text))
	fmt.Println(strings.Contains(text, "Go"))
	fmt.Println(strings.HasPrefix(text, "Hello"))
	fmt.Println(strings.HasSuffix(text, "Programming"))
}
```

## UTF-8 / Khmer

For Unicode text, use runes when counting characters rather than raw bytes.

```go
package main

import "fmt"

func main() {
	text := "សួស្តី"

	fmt.Println("Bytes:", len(text))

	runes := []rune(text)

	fmt.Println("Characters:", len(runes))
}
```

## ខ្មែរ

`len(string)` រាប់ជា **bytes**, មិនមែនចំនួនអក្សរ Unicode ទេ។

សម្រាប់ Khmer/Unicode អាចប្រើ:

```go
[]rune(text)
```

---

# 22. Pointers

A pointer stores a memory address.

```go
package main

import "fmt"

func main() {
	x := 10

	p := &x

	fmt.Println("Value:", x)
	fmt.Println("Address:", p)
	fmt.Println("Value through pointer:", *p)
}
```

Modify through pointer:

```go
package main

import "fmt"

func change(value *int) {
	*value = 100
}

func main() {
	number := 10

	change(&number)

	fmt.Println(number)
}
```

Output:

```text
100
```

## ខ្មែរ

* `&x` → address របស់ `x`
* `*p` → value ដែល pointer `p` ចង្អុលទៅ
* Pointer អាចប្រើដើម្បីកែ value របស់ variable ពី function។

---

# 23. Structs

Struct groups related data.

```go
package main

import "fmt"

type User struct {
	Name  string
	Age   int
	Email string
}

func main() {
	user := User{
		Name:  "Dara",
		Age:   20,
		Email: "dara@example.com",
	}

	fmt.Println(user.Name)
	fmt.Println(user.Age)
	fmt.Println(user.Email)
}
```

Modify:

```go
user.Age = 21
```

Anonymous struct:

```go
package main

import "fmt"

func main() {
	user := struct {
		Name string
		Age  int
	}{
		Name: "Dara",
		Age:  20,
	}

	fmt.Println(user)
}
```

---

# 24. Methods

A method is a function associated with a type.

```go
package main

import "fmt"

type User struct {
	Name string
}

func (u User) Greet() {
	fmt.Println("Hello,", u.Name)
}

func main() {
	user := User{Name: "Dara"}

	user.Greet()
}
```

Pointer receiver:

```go
package main

import "fmt"

type Counter struct {
	Value int
}

func (c *Counter) Increment() {
	c.Value++
}

func main() {
	counter := Counter{}

	counter.Increment()
	counter.Increment()

	fmt.Println(counter.Value)
}
```

Output:

```text
2
```

---

# 25. Interfaces

Interfaces define behavior.

```go
package main

import "fmt"

type Speaker interface {
	Speak()
}

type Dog struct{}

func (Dog) Speak() {
	fmt.Println("Woof!")
}

type Cat struct{}

func (Cat) Speak() {
	fmt.Println("Meow!")
}

func makeSpeak(s Speaker) {
	s.Speak()
}

func main() {
	dog := Dog{}
	cat := Cat{}

	makeSpeak(dog)
	makeSpeak(cat)
}
```

## ខ្មែរ

Interface មិនប្រាប់ថា object ត្រូវជា type អ្វីទេ។

វាប្រាប់ថា object ត្រូវមាន **method អ្វីខ្លះ**។

---

# 26. Embedding

Go supports type embedding.

```go
package main

import "fmt"

type Address struct {
	City    string
	Country string
}

type User struct {
	Name string
	Address
}

func main() {
	user := User{
		Name: "Dara",
		Address: Address{
			City:    "Phnom Penh",
			Country: "Cambodia",
		},
	}

	fmt.Println(user.Name)
	fmt.Println(user.City)
	fmt.Println(user.Country)
}
```

---

# 27. Error Handling

Go commonly handles errors explicitly.

```go
package main

import (
	"errors"
	"fmt"
)

func divide(a, b float64) (float64, error) {
	if b == 0 {
		return 0, errors.New("cannot divide by zero")
	}

	return a / b, nil
}

func main() {
	result, err := divide(10, 0)

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println(result)
}
```

Common pattern:

```go
result, err := someFunction()

if err != nil {
	return err
}
```

## ខ្មែរ

Go មិនប្រើ traditional `try/catch` សម្រាប់ error handling ទេ។

ភាគច្រើនប្រើ:

```go
value, err := function()

if err != nil {
	// handle error
}
```

---

# 28. Custom Errors

Create custom error types.

```go
package main

import (
	"errors"
	"fmt"
)

var ErrInsufficientBalance = errors.New("insufficient balance")

func withdraw(balance, amount float64) (float64, error) {
	if amount > balance {
		return balance, ErrInsufficientBalance
	}

	return balance - amount, nil
}

func main() {
	balance, err := withdraw(100, 150)

	if err != nil {
		if errors.Is(err, ErrInsufficientBalance) {
			fmt.Println("Not enough balance")
			return
		}

		fmt.Println("Error:", err)
		return
	}

	fmt.Println("Remaining:", balance)
}
```

---

# 29. Packages

A package groups related Go code.

Example:

```text
myapp/
├── go.mod
├── main.go
└── calculator/
    └── calculator.go
```

`calculator/calculator.go`:

```go
package calculator

func Add(a, b int) int {
	return a + b
}

func Multiply(a, b int) int {
	return a * b
}
```

`main.go`:

```go
package main

import (
	"fmt"

	"example.com/myapp/calculator"
)

func main() {
	fmt.Println(calculator.Add(10, 20))
	fmt.Println(calculator.Multiply(5, 4))
}
```

## Important

An identifier beginning with an uppercase letter is exported:

```go
func Add()
```

An identifier beginning with lowercase is package-private:

```go
func add()
```

---

# 30. Go Modules

Initialize:

```bash
go mod init example.com/myapp
```

Example `go.mod`:

```go
module example.com/myapp

go 1.24
```

> Use the Go version installed in your development environment when initializing a real project.

Download dependencies:

```bash
go mod tidy
```

Download module dependencies:

```bash
go mod download
```

Run:

```bash
go run .
```

Build:

```bash
go build ./...
```

---

# 31. Goroutines

Goroutines allow functions to run concurrently.

```go
package main

import (
	"fmt"
	"time"
)

func printMessage(message string) {
	for i := 0; i < 3; i++ {
		fmt.Println(message)
		time.Sleep(100 * time.Millisecond)
	}
}

func main() {
	go printMessage("Hello")

	printMessage("World")

	time.Sleep(500 * time.Millisecond)
}
```

Start a goroutine:

```go
go functionName()
```

## ខ្មែរ

Goroutine គឺជា lightweight concurrent execution unit របស់ Go។

វាជាមូលហេតុមួយដែល Go ពេញនិយមសម្រាប់:

* Servers
* APIs
* Networking
* Microservices
* Concurrent tasks

---

# 32. Channels

Channels allow goroutines to communicate.

```go
package main

import "fmt"

func sendMessage(ch chan string) {
	ch <- "Hello from goroutine"
}

func main() {
	ch := make(chan string)

	go sendMessage(ch)

	message := <-ch

	fmt.Println(message)
}
```

Send:

```go
ch <- value
```

Receive:

```go
value := <-ch
```

---

# 33. Buffered Channels

A buffered channel has capacity.

```go
package main

import "fmt"

func main() {
	ch := make(chan string, 2)

	ch <- "Hello"
	ch <- "Go"

	fmt.Println(<-ch)
	fmt.Println(<-ch)
}
```

The channel can store two values before a send blocks.

---

# 34. Select

`select` waits for channel operations.

```go
package main

import "fmt"

func main() {
	ch1 := make(chan string)
	ch2 := make(chan string)

	go func() {
		ch1 <- "Message from channel 1"
	}()

	go func() {
		ch2 <- "Message from channel 2"
	}()

	select {
	case message := <-ch1:
		fmt.Println(message)
	case message := <-ch2:
		fmt.Println(message)
	}
}
```

## Timeout example

```go
package main

import (
	"fmt"
	"time"
)

func main() {
	ch := make(chan string)

	go func() {
		time.Sleep(2 * time.Second)
		ch <- "Finished"
	}()

	select {
	case message := <-ch:
		fmt.Println(message)

	case <-time.After(1 * time.Second):
		fmt.Println("Timeout")
	}
}
```

---

# 35. WaitGroup

`sync.WaitGroup` waits for multiple goroutines.

```go
package main

import (
	"fmt"
	"sync"
)

func worker(id int, wg *sync.WaitGroup) {
	defer wg.Done()

	fmt.Println("Worker:", id)
}

func main() {
	var wg sync.WaitGroup

	for i := 1; i <= 5; i++ {
		wg.Add(1)

		go worker(i, &wg)
	}

	wg.Wait()

	fmt.Println("All workers finished")
}
```

Important pattern:

```go
wg.Add(1)
go worker(...)
wg.Wait()
```

---

# 36. Mutex

A mutex protects shared data.

Unsafe example concept:

```text
Multiple goroutines
       ↓
Shared variable
       ↓
Race condition
```

Safe example:

```go
package main

import (
	"fmt"
	"sync"
)

type Counter struct {
	mu    sync.Mutex
	value int
}

func (c *Counter) Increment() {
	c.mu.Lock()
	defer c.mu.Unlock()

	c.value++
}

func main() {
	counter := &Counter{}

	var wg sync.WaitGroup

	for i := 0; i < 1000; i++ {
		wg.Add(1)

		go func() {
			defer wg.Done()
			counter.Increment()
		}()
	}

	wg.Wait()

	fmt.Println(counter.value)
}
```

Expected output:

```text
1000
```

---

# 37. Context

`context.Context` is commonly used to control cancellation, deadlines, and request-scoped values.

```go
package main

import (
	"context"
	"fmt"
	"time"
)

func worker(ctx context.Context) {
	for {
		select {
		case <-ctx.Done():
			fmt.Println("Worker stopped")
			return

		default:
			fmt.Println("Working...")
			time.Sleep(200 * time.Millisecond)
		}
	}
}

func main() {
	ctx, cancel := context.WithCancel(context.Background())

	go worker(ctx)

	time.Sleep(1 * time.Second)

	cancel()

	time.Sleep(100 * time.Millisecond)
}
```

## ខ្មែរ

Context មានប្រយោជន៍ខ្លាំងសម្រាប់:

* HTTP requests
* Timeouts
* Cancellation
* Database operations
* Goroutines

---

# 38. Generics

Generics allow reusable code with type parameters.

```go
package main

import "fmt"

func Max[T int | float64](a, b T) T {
	if a > b {
		return a
	}

	return b
}

func main() {
	fmt.Println(Max(10, 20))
	fmt.Println(Max(10.5, 20.5))
}
```

Generic slice function:

```go
package main

import "fmt"

func Contains[T comparable](items []T, target T) bool {
	for _, item := range items {
		if item == target {
			return true
		}
	}

	return false
}

func main() {
	numbers := []int{1, 2, 3, 4}

	fmt.Println(Contains(numbers, 3))
	fmt.Println(Contains(numbers, 10))
}
```

## ខ្មែរ

Generics អនុញ្ញាតឱ្យយើងសរសេរ function/type ដែលអាចប្រើជាមួយ data type ច្រើន ដោយមិនចាំបាច់ duplicate code។

---

# 39. Reflection

Reflection allows a program to inspect types and values at runtime.

```go
package main

import (
	"fmt"
	"reflect"
)

type User struct {
	Name string
	Age  int
}

func main() {
	user := User{
		Name: "Dara",
		Age:  20,
	}

	value := reflect.ValueOf(user)
	typeInfo := reflect.TypeOf(user)

	fmt.Println("Type:", typeInfo)
	fmt.Println("Fields:", value.NumField())

	for i := 0; i < value.NumField(); i++ {
		fmt.Println(value.Field(i))
	}
}
```

## Important

Reflection is powerful, but should not be used when normal Go code is simpler.

---

# 40. JSON

Go provides `encoding/json`.

Struct to JSON:

```go
package main

import (
	"encoding/json"
	"fmt"
)

type User struct {
	Name  string `json:"name"`
	Age   int    `json:"age"`
	Email string `json:"email"`
}

func main() {
	user := User{
		Name:  "Dara",
		Age:   20,
		Email: "dara@example.com",
	}

	data, err := json.Marshal(user)

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println(string(data))
}
```

Output:

```json
{"name":"Dara","age":20,"email":"dara@example.com"}
```

JSON to struct:

```go
package main

import (
	"encoding/json"
	"fmt"
)

type User struct {
	Name string `json:"name"`
	Age  int    `json:"age"`
}

func main() {
	data := []byte(`{"name":"Dara","age":20}`)

	var user User

	err := json.Unmarshal(data, &user)

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println(user.Name)
	fmt.Println(user.Age)
}
```

---

# 41. File Handling

Create/write a file:

```go
package main

import (
	"fmt"
	"os"
)

func main() {
	data := []byte("Hello from Go!")

	err := os.WriteFile("hello.txt", data, 0644)

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println("File written successfully")
}
```

Read:

```go
package main

import (
	"fmt"
	"os"
)

func main() {
	data, err := os.ReadFile("hello.txt")

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println(string(data))
}
```

---

# 42. HTTP Server

Go has a built-in HTTP server package.

```go
package main

import (
	"fmt"
	"net/http"
)

func homeHandler(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintln(w, "Hello from Go HTTP Server!")
}

func main() {
	http.HandleFunc("/", homeHandler)

	fmt.Println("Server running on http://localhost:8080")

	err := http.ListenAndServe(":8080", nil)

	if err != nil {
		fmt.Println("Server error:", err)
	}
}
```

Run:

```bash
go run .
```

Open:

```text
http://localhost:8080
```

---

# 43. HTTP Client

Send a GET request:

```go
package main

import (
	"fmt"
	"io"
	"net/http"
)

func main() {
	response, err := http.Get("https://example.com")

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	defer response.Body.Close()

	body, err := io.ReadAll(response.Body)

	if err != nil {
		fmt.Println("Error:", err)
		return
	}

	fmt.Println("Status:", response.Status)
	fmt.Println(string(body))
}
```

---

# 44. REST API

A simple JSON REST API:

```go
package main

import (
	"encoding/json"
	"net/http"
)

type User struct {
	ID   int    `json:"id"`
	Name string `json:"name"`
}

func usersHandler(w http.ResponseWriter, r *http.Request) {
	users := []User{
		{ID: 1, Name: "Dara"},
		{ID: 2, Name: "Sok"},
	}

	w.Header().Set("Content-Type", "application/json")

	err := json.NewEncoder(w).Encode(users)

	if err != nil {
		http.Error(w, "Internal Server Error", http.StatusInternalServerError)
		return
	}
}

func main() {
	http.HandleFunc("/api/users", usersHandler)

	http.ListenAndServe(":8080", nil)
}
```

Request:

```text
GET /api/users
```

Response:

```json
[
	{
		"id": 1,
		"name": "Dara"
	},
	{
		"id": 2,
		"name": "Sok"
	}
]
```

---

# 45. Middleware

Middleware wraps an HTTP handler.

```go
package main

import (
	"fmt"
	"net/http"
	"time"
)

func loggingMiddleware(next http.Handler) http.Handler {
	return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
		start := time.Now()

		next.ServeHTTP(w, r)

		fmt.Println(
			r.Method,
			r.URL.Path,
			time.Since(start),
		)
	})
}

func homeHandler(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintln(w, "Hello!")
}

func main() {
	handler := loggingMiddleware(http.HandlerFunc(homeHandler))

	http.Handle("/", handler)

	fmt.Println("Server running on :8080")

	err := http.ListenAndServe(":8080", nil)

	if err != nil {
		fmt.Println(err)
	}
}
```

Common middleware uses:

* Logging
* Authentication
* Authorization
* CORS
* Rate limiting
* Request IDs
* Recovery
* Metrics

---

# 46. Testing

Go has built-in testing support.

Create:

```text
calculator.go
calculator_test.go
```

`calculator.go`:

```go
package calculator

func Add(a, b int) int {
	return a + b
}
```

`calculator_test.go`:

```go
package calculator

import "testing"

func TestAdd(t *testing.T) {
	result := Add(10, 20)

	expected := 30

	if result != expected {
		t.Fatalf("expected %d, got %d", expected, result)
	}
}
```

Run:

```bash
go test ./...
```

Verbose:

```bash
go test -v ./...
```

---

# 47. Benchmarks

Go supports benchmarks.

```go
package calculator

import "testing"

func Add(a, b int) int {
	return a + b
}

func BenchmarkAdd(b *testing.B) {
	for i := 0; i < b.N; i++ {
		Add(10, 20)
	}
}
```

Run:

```bash
go test -bench=.
```

---

# 48. Dependency Injection

Dependency Injection means passing dependencies instead of creating them inside the object/function.

Example:

```go
package main

import "fmt"

type Logger interface {
	Log(message string)
}

type ConsoleLogger struct{}

func (ConsoleLogger) Log(message string) {
	fmt.Println(message)
}

type UserService struct {
	logger Logger
}

func NewUserService(logger Logger) *UserService {
	return &UserService{
		logger: logger,
	}
}

func (s *UserService) CreateUser(name string) {
	s.logger.Log("Creating user: " + name)
}

func main() {
	logger := ConsoleLogger{}

	service := NewUserService(logger)

	service.CreateUser("Dara")
}
```

## Why?

Dependency Injection makes code:

* Easier to test
* Easier to maintain
* More flexible
* Less tightly coupled

---

# 49. Clean Project Structure

A larger Go API project can use a structure such as:

```text
my-api/
│
├── cmd/
│   └── server/
│       └── main.go
│
├── internal/
│   ├── handler/
│   ├── service/
│   ├── repository/
│   ├── model/
│   └── middleware/
│
├── pkg/
│   └── response/
│
├── migrations/
│
├── configs/
│
├── tests/
│
├── go.mod
├── go.sum
└── README.md
```

## Responsibility

### `cmd/`

Application entry points.

### `internal/`

Private application code that should not be imported by external modules.

### `pkg/`

Reusable packages intended for broader reuse.

### `handler/`

HTTP request handling.

### `service/`

Business logic.

### `repository/`

Database/data-access logic.

### `model/`

Data structures.

### `middleware/`

HTTP middleware.

---

# 50. Advanced Concurrency

## Worker Pool

A worker pool is useful when many jobs must be processed by a limited number of workers.

```go
package main

import (
	"fmt"
	"sync"
)

type Job struct {
	ID int
}

func worker(id int, jobs <-chan Job, wg *sync.WaitGroup) {
	defer wg.Done()

	for job := range jobs {
		fmt.Printf("Worker %d processing job %d\n", id, job.ID)
	}
}

func main() {
	jobs := make(chan Job)

	var wg sync.WaitGroup

	workerCount := 3

	for i := 1; i <= workerCount; i++ {
		wg.Add(1)

		go worker(i, jobs, &wg)
	}

	for i := 1; i <= 10; i++ {
		jobs <- Job{ID: i}
	}

	close(jobs)

	wg.Wait()

	fmt.Println("All jobs completed")
}
```

## ខ្មែរ

Worker Pool គឺជា pattern ដែលមាន:

```text
Jobs
  ↓
Job Queue
  ↓
Worker 1
Worker 2
Worker 3
  ↓
Result
```

វាជួយកំណត់ចំនួន concurrent workers ដើម្បីជៀសវាងការបង្កើត goroutines ច្រើនពេក។

---

# 51. Best Practices

## 1. Format your code

Always use:

```bash
gofmt -w .
```

---

## 2. Check errors

Bad:

```go
result, _ := someFunction()
```

Better:

```go
result, err := someFunction()

if err != nil {
	return err
}
```

---

## 3. Keep functions small

Bad:

```go
func doEverything() {
	// 500 lines
}
```

Better:

```go
func validateUser() {}
func createUser() {}
func sendEmail() {}
```

---

## 4. Use meaningful names

Bad:

```go
x := 20
```

Better:

```go
userAge := 20
```

---

## 5. Avoid unnecessary interfaces

Do not create interfaces just because you can.

Use interfaces when abstraction or substitution is actually useful.

---

## 6. Prefer simple Go code

Go values:

> Simple code is often better code.

Avoid unnecessary abstraction.

---

## 7. Handle errors close to where they occur

```go
data, err := os.ReadFile("config.json")

if err != nil {
	return fmt.Errorf("read config: %w", err)
}
```

The `%w` verb wraps an error so it can later be inspected with functions such as `errors.Is` and `errors.As`.

---

## 8. Use context for cancellation

For server/database operations:

```go
func Process(ctx context.Context) error {
	// ...
	return nil
}
```

---

## 9. Test your code

```bash
go test ./...
```

---

## 10. Detect race conditions

Use:

```bash
go test -race ./...
```

This is especially useful when working with:

* Goroutines
* Channels
* Shared memory
* Mutexes

---

# 52. Learning Roadmap

## 🟢 Beginner

Learn these first:

```text
1. Go installation
2. package main
3. main()
4. Variables
5. Constants
6. Data types
7. Operators
8. Input/output
9. if/else
10. switch
11. for
12. Functions
13. Arrays
14. Slices
15. Maps
16. Strings
```

### Khmer

ដំបូងគួររៀន:

```text
Variables
Data Types
Conditions
Loops
Functions
Arrays
Slices
Maps
Strings
```

---

# 🟡 Intermediate

Next learn:

```text
1. Pointers
2. Structs
3. Methods
4. Interfaces
5. Packages
6. Modules
7. Error handling
8. File handling
9. JSON
10. HTTP
11. REST API
12. Testing
13. Middleware
```

### Khmer

កម្រិត Intermediate ត្រូវចាប់ផ្តើមយល់ពី:

```text
Struct
Pointer
Method
Interface
Package
Error
JSON
HTTP
REST API
Testing
```

---

# 🔴 Advanced

Then learn:

```text
1. Goroutines
2. Channels
3. Select
4. WaitGroup
5. Mutex
6. Context
7. Worker pools
8. Generics
9. Reflection
10. Dependency Injection
11. Concurrency patterns
12. Performance
13. Race detection
14. Distributed systems
15. Microservices
```

---

# 🧠 Complete Go Learning Path

```text
                    GO
                     │
        ┌────────────┴────────────┐
        │                         │
     Beginner                 Intermediate
        │                         │
   Variables                    Structs
   Types                        Methods
   Conditions                   Interfaces
   Loops                        Packages
   Functions                    Errors
   Slices                       JSON
   Maps                         HTTP
        │                         │
        └────────────┬────────────┘
                     │
                  Advanced
                     │
              ┌──────┴──────┐
              │             │
         Concurrency      Backend
              │             │
         Goroutines       REST API
         Channels         Middleware
         Select           Database
         Mutex            Authentication
         Context          Testing
              │             │
              └──────┬──────┘
                     │
                Professional
                     │
          Microservices / Cloud
                     │
              Distributed Systems
```

---

# 🚀 Example: Complete Mini Go API

Here is a small complete API using only Go's standard library.

## Project

```text
go-api/
├── go.mod
└── main.go
```

## `go.mod`

```go
module example.com/go-api

go 1.24
```

## `main.go`

```go
package main

import (
	"encoding/json"
	"log"
	"net/http"
	"strconv"
	"strings"
)

type User struct {
	ID    int    `json:"id"`
	Name  string `json:"name"`
	Email string `json:"email"`
}

var users = []User{
	{
		ID:    1,
		Name:  "Dara",
		Email: "dara@example.com",
	},
	{
		ID:    2,
		Name:  "Sok",
		Email: "sok@example.com",
	},
}

func usersHandler(w http.ResponseWriter, r *http.Request) {
	w.Header().Set("Content-Type", "application/json")

	switch r.Method {
	case http.MethodGet:
		if err := json.NewEncoder(w).Encode(users); err != nil {
			http.Error(
				w,
				"Internal Server Error",
				http.StatusInternalServerError,
			)
		}

	case http.MethodPost:
		var user User

		if err := json.NewDecoder(r.Body).Decode(&user); err != nil {
			http.Error(
				w,
				"Invalid JSON",
				http.StatusBadRequest,
			)
			return
		}

		user.ID = len(users) + 1

		users = append(users, user)

		w.WriteHeader(http.StatusCreated)

		if err := json.NewEncoder(w).Encode(user); err != nil {
			http.Error(
				w,
				"Internal Server Error",
				http.StatusInternalServerError,
			)
		}

	default:
		w.Header().Set("Allow", "GET, POST")

		http.Error(
			w,
			"Method Not Allowed",
			http.StatusMethodNotAllowed,
		)
	}
}

func userHandler(w http.ResponseWriter, r *http.Request) {
	if r.Method != http.MethodGet {
		w.Header().Set("Allow", http.MethodGet)

		http.Error(
			w,
			"Method Not Allowed",
			http.StatusMethodNotAllowed,
		)

		return
	}

	idText := strings.TrimPrefix(r.URL.Path, "/api/users/")

	id, err := strconv.Atoi(idText)

	if err != nil {
		http.Error(
			w,
			"Invalid user ID",
			http.StatusBadRequest,
		)
		return
	}

	for _, user := range users {
		if user.ID == id {
			w.Header().Set("Content-Type", "application/json")

			if err := json.NewEncoder(w).Encode(user); err != nil {
				http.Error(
					w,
					"Internal Server Error",
					http.StatusInternalServerError,
				)
			}

			return
		}
	}

	http.Error(
		w,
		"User not found",
		http.StatusNotFound,
	)
}

func main() {
	mux := http.NewServeMux()

	mux.HandleFunc("/api/users", usersHandler)
	mux.HandleFunc("/api/users/", userHandler)

	log.Println("Server running on http://localhost:8080")

	if err := http.ListenAndServe(":8080", mux); err != nil {
		log.Fatal(err)
	}
}
```

Run:

```bash
go mod tidy
go run .
```

Test:

```bash
curl http://localhost:8080/api/users
```

Create a user:

```bash
curl -X POST http://localhost:8080/api/users \
  -H "Content-Type: application/json" \
  -d "{\"name\":\"Chan\",\"email\":\"chan@example.com\"}"
```

Get one user:

```bash
curl http://localhost:8080/api/users/1
```

---

# 🏗️ Recommended Professional Go Architecture

For a production backend, you can gradually move toward:

```text
project/
│
├── cmd/
│   └── api/
│       └── main.go
│
├── internal/
│   │
│   ├── handler/
│   │   └── user_handler.go
│   │
│   ├── service/
│   │   └── user_service.go
│   │
│   ├── repository/
│   │   └── user_repository.go
│   │
│   ├── model/
│   │   └── user.go
│   │
│   ├── middleware/
│   │   └── auth.go
│   │
│   └── config/
│       └── config.go
│
├── migrations/
│
├── tests/
│
├── go.mod
├── go.sum
├── .gitignore
└── README.md
```

Typical request flow:

```text
Client
  │
  ▼
HTTP Router
  │
  ▼
Middleware
  │
  ▼
Handler
  │
  ▼
Service
  │
  ▼
Repository
  │
  ▼
Database
```

### Khmer

Architecture នេះបែងចែក responsibility ឱ្យច្បាស់៖

```text
Handler
   ↓
ទទួល HTTP Request

Service
   ↓
Business Logic

Repository
   ↓
Database Logic

Model
   ↓
Data Structure
```

វាធ្វើឱ្យ project ធំៗងាយ:

* Maintain
* Test
* Debug
* Scale
* Collaborate

---

# 🛠️ Useful Go Commands

Create module:

```bash
go mod init example.com/project
```

Run:

```bash
go run .
```

Build:

```bash
go build
```

Build all packages:

```bash
go build ./...
```

Test:

```bash
go test ./...
```

Verbose tests:

```bash
go test -v ./...
```

Race detector:

```bash
go test -race ./...
```

Benchmark:

```bash
go test -bench=.
```

Format:

```bash
gofmt -w .
```

Check dependencies:

```bash
go mod tidy
```

Download dependencies:

```bash
go mod download
```

List packages:

```bash
go list ./...
```

---

# 📌 Go Cheat Sheet

## Variables

```go
name := "Dara"
age := 20
```

## Constant

```go
const Pi = 3.14159
```

## Condition

```go
if age >= 18 {
	fmt.Println("Adult")
}
```

## Loop

```go
for i := 0; i < 10; i++ {
	fmt.Println(i)
}
```

## Function

```go
func add(a, b int) int {
	return a + b
}
```

## Slice

```go
numbers := []int{1, 2, 3}
```

## Map

```go
users := map[string]int{
	"Dara": 20,
}
```

## Struct

```go
type User struct {
	Name string
	Age  int
}
```

## Pointer

```go
p := &value
```

## Method

```go
func (u User) Greet() {
}
```

## Interface

```go
type Speaker interface {
	Speak()
}
```

## Goroutine

```go
go function()
```

## Channel

```go
ch := make(chan int)
```

## Send

```go
ch <- 10
```

## Receive

```go
value := <-ch
```

## Context

```go
ctx, cancel := context.WithCancel(context.Background())
defer cancel()
```

## Error

```go
value, err := function()

if err != nil {
	return err
}
```

---

# 🎯 Projects to Practice

## Beginner Projects

Build:

1. Calculator
2. Number guessing game
3. Todo CLI
4. Temperature converter
5. Unit converter
6. Student grade system
7. Simple banking CLI
8. Contact manager

---

## Intermediate Projects

Build:

1. Todo REST API
2. User management API
3. Authentication API
4. Blog API
5. URL shortener
6. File upload API
7. CLI application
8. PostgreSQL CRUD API

---

## Advanced Projects

Build:

1. E-commerce backend
2. Payment service
3. Chat server
4. Notification service
5. URL shortener with caching
6. Job queue
7. Worker pool
8. Microservice system
9. API gateway
10. Distributed task processing system

---

# 🧩 Recommended Learning Order

Follow this order:

```text
01. Syntax
      ↓
02. Variables & Types
      ↓
03. Conditions
      ↓
04. Loops
      ↓
05. Functions
      ↓
06. Arrays & Slices
      ↓
07. Maps
      ↓
08. Structs
      ↓
09. Pointers
      ↓
10. Methods
      ↓
11. Interfaces
      ↓
12. Packages
      ↓
13. Modules
      ↓
14. Error Handling
      ↓
15. JSON
      ↓
16. Files
      ↓
17. HTTP
      ↓
18. REST API
      ↓
19. Testing
      ↓
20. Goroutines
      ↓
21. Channels
      ↓
22. Context
      ↓
23. Mutex
      ↓
24. Generics
      ↓
25. Dependency Injection
      ↓
26. Database
      ↓
27. Authentication
      ↓
28. Clean Architecture
      ↓
29. Microservices
      ↓
30. Distributed Systems
```

---

# 🌟 What You Should Understand After This Guide

After completing these topics, you should understand:

### Beginner

```text
✓ Go syntax
✓ Variables
✓ Types
✓ Operators
✓ Conditions
✓ Loops
✓ Functions
✓ Arrays
✓ Slices
✓ Maps
✓ Strings
```

### Intermediate

```text
✓ Pointers
✓ Structs
✓ Methods
✓ Interfaces
✓ Packages
✓ Modules
✓ Error handling
✓ JSON
✓ Files
✓ HTTP
✓ REST APIs
✓ Testing
```

### Advanced

```text
✓ Goroutines
✓ Channels
✓ Select
✓ Mutex
✓ WaitGroup
✓ Context
✓ Worker pools
✓ Generics
✓ Reflection
✓ Dependency Injection
✓ Concurrency
✓ Performance
✓ Production architecture
```

---

# 🏁 Final Goal

The goal is not just to memorize Go syntax.

You should be able to build:

```text
                 Go Developer
                      │
          ┌───────────┴───────────┐
          │                       │
       Language                Backend
          │                       │
    ┌─────┴─────┐          ┌──────┴──────┐
    │           │          │             │
 Syntax    Concurrency    REST API     Database
    │           │          │             │
    └─────┬─────┘          └──────┬──────┘
          │                       │
          └───────────┬───────────┘
                      │
                Production App
                      │
          ┌───────────┴───────────┐
          │                       │
      Testing                 Deployment
          │                       │
      Security                 Docker
          │                       │
      Monitoring                Cloud
```

---

# 📖 Summary

Go is especially useful when you want to build:

* ⚡ Fast backend services
* 🌐 REST APIs
* ☁️ Cloud applications
* 🔄 Concurrent systems
* 🧩 Microservices
* 🛠️ CLI tools
* 🌍 Networking applications
* 🚀 Scalable services

The most important concepts to master are:

```text
Functions
    ↓
Structs
    ↓
Interfaces
    ↓
Errors
    ↓
Packages
    ↓
HTTP
    ↓
Goroutines
    ↓
Channels
    ↓
Context
    ↓
Testing
    ↓
Architecture
```

> **Learn the basics deeply before moving to advanced concurrency and architecture.**
>
> **រៀន Basic ឱ្យរឹងមាំសិន មុនពេលចូលទៅ Concurrency, API និង Architecture។**

---

# ⭐ Keep Learning

```text
Learn
  ↓
Code
  ↓
Build
  ↓
Test
  ↓
Debug
  ↓
Refactor
  ↓
Build bigger projects
```

**Happy Coding with Go! 🐹🚀**
