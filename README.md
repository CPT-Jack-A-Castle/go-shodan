# go-shodan
[![Build Status](https://travis-ci.org/ns3777k/go-shodan.svg?branch=master)](https://travis-ci.org/ns3777k/go-shodan)
[![Coverage Status](https://coveralls.io/repos/ns3777k/go-shodan/badge.svg?branch=master&service=github)](https://coveralls.io/github/ns3777k/go-shodan?branch=master)
[![GoDoc](https://godoc.org/github.com/ns3777k/go-shodan/shodan?status.svg)](https://godoc.org/github.com/ns3777k/go-shodan/shodan)

To start working with Shodan you have to get your token first. You can do this at [http://www.shodanhq.com](http://www.shodanhq.com).

### Installation
Download the package:

```bash
go get "github.com/ns3777k/go-shodan/shodan"
```

Start using it:
```go
package main

import (
    "log"
    
    "github.com/ns3777k/go-shodan/shodan"
)

func main() {
    client := shodan.NewClient("MY_TOKEN")
    dns, err := client.GetDNSResolve([]string{"google.com", "ya.ru"})
    
    if err != nil {
        log.Panic(err)
    } else {
        log.Println(dns["google.com"])
    }
}
```
Output for above:
```bash
2015/09/05 18:50:52 173.194.115.35
```

### Roadmap
1. Streaming API
2. Testing
3. Scan API? (Don't have scan credits though)

### Links
* [Shodan.io](http://shodan.io) & [ShodanHQ](http://www.shodanhq.com)
* [API Documentation](https://developer.shodan.io/api)
