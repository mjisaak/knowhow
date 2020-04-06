# Notes about Go

## Install / Setup VSCode

### Install GO

[Download the installer](https://golang.org/dl/) and run it.

### Install Delve

Delve can be installed using the `go get` command:

```bash
go get -u github.com/go-delve/delve/cmd/dlv
```

More information here: [Installation on Windows](https://github.com/go-delve/delve/blob/master/Documentation/installation/windows/install.md#installation-on-windows)

### Enable Go Language server

Set the `go.useLanguageServer` VSCode Setting to `true`:

![go-vscode-language-server](/img/2020-03-22-11-33-38.png)  

### Install Go Tools

Open the ```Go: Install/Update Tools``` dialog using the Command Palette (<kbd>Strg</kbd> + <kbd>Shift</kbd> + <kbd>p</kbd>) and select all:

![Go Install/Update Tools](/img/2020-03-22-11-28-40.png)

### Test the installation

Create a file named `hello.go` and add the following content to it:

```go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello, world!")
}

```

You should now be able to start debugging the package using <kbd>F5</kbd>

## Snippets (learned from tour.golang.org)

## Arrays

```go
	myList = []int{1, 2, 3}
	myList = append(myList, 4, 5)

	for v := range myList {
		fmt.Println(myList[v])
	}
```

## Arrays II

```go
package main

import (
	"fmt"
)

type Player struct {
	Name string
	Age  int
}

func main() {

	players := []Player{
		{Name: "Martin", Age: 3},
	}

	for _, v := range players {
		fmt.Println(v.Name)
	}

}

```

### Slices

#### Slices of slices

```go
	board := [][]string{
		[]string{"_", "_", "_"},
		[]string{"_", "_", "_"},
		[]string{"_", "_", "_"},
	}

	board[0][0] = "X"
	board[2][2] = "O"
	board[1][2] = "X"
	board[1][0] = "O"
	board[0][2] = "X"
```

#### Append to slices

```go

	var s []int
	var y []int

	s = append(s, 3)
	s = append(s, 5)

	y = append(s, 1)

	fmt.Println("s: ", s)
	fmt.Println("y: ", y)
```

### Structs

```go
package main

import (
	"fmt"
)

type Player struct {
	fartingPower int
	name         string
}

func main() {

	players := []Player{
		Player{fartingPower: 3, name: "Martin"},
	}

	fmt.Println("yo", players)
}
```

### Maps

```go
package main

import (
	"fmt"
)

type Player struct {
	Name string
	Age  int
}

func main() {

	// var m map[string]Player
	m := make(map[string]Player)

	m["Martin"] = Player{"Martin JI Brandl", 34}
	_, ok := m["Martin2"]
	
	fmt.Println("present:", ok)
	fmt.Println(m["Martin"])

}
```