go-tty - Terminal control library for Go
======================================================================

  * Copyright (C) 2014 SATOH Fumiyasu @ OSS Technology Corp., Japan
  * License: MIT License
  * Development home: <https://github.com/fumiyas/go-tty>
  * Author's home: <https://fumiyas.github.io/>

What's this?
---------------------------------------------------------------------

This is a set of terminal control library for Go.

Usage
---------------------------------------------------------------------

### tty.IsTty(os.Stdout)

```go
package main

import (
	"os"
	"fmt"
	"github.com/fumiyas/go-tty"
)

func main() {
	fmt.Print("stdin is ")
	if !tty.IsTty(os.Stdin) {
	  fmt.Print("not ")
	}
	fmt.Print("a tty.\n")
}
```

### tty.GetDeviceAttributes1(os.Stdout)

```go
package main

import (
	"os"
	"fmt"
	"github.com/fumiyas/go-tty"
)

func main() {
	da1, err := tty.GetDeviceAttributes1(os.Stdout)
	if err == nil && da1[tty.DA1_SIXEL] {
		fmt.Printf("\x1BPq#0;2;0;0;0#1;2;100;100;0#2;2;0;0;100#1~~@@vv@@~~@@~~$#2??}}GG}}??}}??-#1!14@\x1B\\")
	} else {
		fmt.Printf("Hi\n")
	}
}
```

Download
---------------------------------------------------------------------

```console
$ go get github.com/fumiyas/go-tty
```

TODO
----------------------------------------------------------------------

Contributors
----------------------------------------------------------------------

Similar products
----------------------------------------------------------------------

