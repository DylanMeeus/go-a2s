## Go A2S

[![Build Status](https://travis-ci.com/rumblefrog/go-a2s.svg?branch=master)](https://travis-ci.com/rumblefrog/go-a2s)
[![Go Report Card](https://goreportcard.com/badge/github.com/rumblefrog/go-a2s)](https://goreportcard.com/report/github.com/rumblefrog/go-a2s)
[![GoDoc](https://godoc.org/github.com/rumblefrog/go-a2s?status.svg)](https://godoc.org/github.com/rumblefrog/go-a2s)

An implementation of [Source A2S Queries](https://developer.valvesoftware.com/wiki/Server_queries)

Godoc is available here: https://godoc.org/github.com/rumblefrog/go-a2s

**Note: Only supports Source engine and above, Goldsource is not supported**

## Guides

### Installing

```bash
go get -u github.com/rumblefrog/go-a2s
```

### Querying

```go
package main

import (
    a2s "https://github.com/rumblefrog/go-a2s"
)

func main() {
    client := a2s.NewClient("ServerIP:Port")

    defer client.Close()

    info, err := client.QueryInfo() // QueryInfo, QueryPlayer, QueryRules

    if err != nil {
        // Handle error
    }

    // ...
}
```

### Setting client options

```go
package main

import (
    a2s "https://github.com/rumblefrog/go-a2s"
)

func main() {
    client := a2s.NewClient(
        "ServerIP:Port",
        a2s.TimeoutOption(time.Second * 5), // Setting timeout option. Default is 3 seconds
        // ... Other options
    )

    defer client.Close()

    // ...
}
```

## Credits
 - Dvander's Blaster for the packet logics
 - xPaw's PHP Source Query for query specific logics
