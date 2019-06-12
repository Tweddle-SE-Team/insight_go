insight_go
=====

Golang client library for InsightOPS

It is compatible with http://golang.org/pkg/log/#Logger
and also implements http://golang.org/pkg/io/#Writer

[![GoDoc](https://godoc.org/github.com/Tweddle-SE-Team/insight_go?status.png)](https://godoc.org/github.com/Tweddle-SE-Team/insight_go)

[![Build Status](https://travis-ci.org/Tweddle-SE-Team/insight_go.svg)](https://travis-ci.org/Tweddle-SE-Team/insight_go)

Usage
-----
Add a new manual TCP token log at [InsightOPS](https://insightops.help.rapid7.com/docs/quick-start-guide) and copy the [token](https://insightops.help.rapid7.com/docs/token-tcp).

Installation: `go get github.com/Tweddle-SE-Team/insight_go`

**Note:** The Logger is blocking, it can be easily run in a goroutine by calling `go insight.Println(...)`

```go
package main

import "github.com/Tweddle-SE-Team/insight_go"

func main() {
	le, err := insight_go.Connect("eu", "XXXX-XXXX-XXXX-XXXX") // replace with token
	if err != nil {
		panic(err)
	}

	defer insight.Close()

	insight.Println("another test message")
}
```

