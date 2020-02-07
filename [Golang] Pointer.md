# Pointer

Go has pointers. A pointer holds the memory address of a value.

The type *T is a pointer to a T value. Its zero value is nil.

```
var p *int
```

The & operator generates a pointer to its operand.

```
i := 42
p = &i
```

The * operator denotes the pointer's underlying value.

```
fmt.Println(*p) // read i through the pointer p
*p = 21         // set i through the pointer p
This is known as "dereferencing" or "indirecting".
```

Unlike C, Go has no pointer arithmetic.

### Example

```
package main

import (
	"fmt"
	"io/ioutil"
)

type Page struct {
	Title string
	Body []byte
}

# This func receives a pointer, like "p1" in main().
# The * operator denotes the pointer's underlying value.
# (p *Page) declares that p is the pointer's underlying value.
func (p *Page) save() error {
	filename := p.Title + ".txt"
	# Return a error code, here is nil.
	return ioutil.WriteFile(filename, p.Body, 0600)
}

func loadPage(title string) (*Page, error) {
	filename := title + ".txt"
	body, err := ioutil.ReadFile(filename)
	if err != nil {
	    return nil, err
	}
	return &Page{Title: title, Body: body}
}

func main() {
	# The & operator generates a pointer to its operand.
	# Now, p1 is the pointer of Page. 
	p1 := &Page{Title: "TestPage", Body: []byte("This is a simple page")}
	p1.save()
	# func loadPage returns &Page, so, p2 is also a pointer.
	p2, _ := loadPage("TestPage")
	fmt.Println(string(p2.Body))
}
```