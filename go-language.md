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

### Slices of slices

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