## gosexy/gettext

``gosexy/gettext`` is a wrapper of [GNU gettext][1], an internationalization and localization library for writing multilingual systems.

## Requeriments

The GNU C library. If you're using GNU/Linux, FreeBSD or OSX you should already have it.

## Installation

Just pull from the repository:

```sh
$ go get github.com/gosexy/gettex
```

## Usage

```go
package main

import (
	"github.com/gosexy/gettext"
	"fmt"
	"os"
)

func main() {
	gettext.BindTextdomain("example", ".")
	gettext.Textdomain("example")

	os.Setenv("LANGUAGE", "es_MX.utf8")

	gettext.SetLocale(gettext.LC_ALL, "")

	fmt.Println(gettext.Gettext("Hello, world!"))
}
```

You can use ``os.Setenv`` to set the ``LANGUAGE`` environment variable or set it from a terminal:

```sh
% export LANGUAGE="es_MX.utf8"
% ./gettext-program
```

## Documentation

You can read ``gosexy/gettext`` documentation from a terminal

```go
% go doc github.com/gosexy/gettext
```

The original gettext documentation can be very useful too:

```go
% man 3 gettext
```

Or you can [browse it](http://go.pkgdoc.org/github.com/gosexy/gettext) online.

[1]: http://www.gnu.org/software/gettext/
