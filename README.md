List
====

* [midjourney-go](#midjourney-go)
* [installation](#installation)
* [simple usage](#simple-usage)
* [features](#features)
* [license](#license)
* [changelog](#changelog)

# midjourney-go #

midjourney-go is a Go client library for accessing the [Midjourney-Bot API](https://midjourney.com/).

It is designed very simply and is lightweight with no additional logic. It belongs to a very low-level library, so you can use it to do anything.

If you want to build your own midjourney apiserver, take a look at this [midjourney-apiserver](https://github.com/hongliang5316/midjourney-apiserver).

[List](#list)

## Installation ##

midjourney-go is compatible with modern Go releases in module mode, with Go installed:

```bash
go get github.com/hongliang5316/midjourney-go@v0.0.1
```

will resolve and add the package to the current development module, along with its dependencies.

Alternatively the same can be achieved if you use import in a package:

```go
import "github.com/hongliang5316/midjourney-go/midjourney"
```

and run `go mod tidy` without parameters.

[List](#list)

## Simple Usage ##

Construct a new `Midjourney client`, then use the various commands on the client to
access different parts of the `Midjourney-Bot API`. For example:

```go
client := midjourney.NewClient(&midjourney.Config{
    UserToken: "your token",
})

// imagine
if err := client.Imagine(context.Background(), &midjourney.ImagineRequest{
    GuildID: "",
    ChannelID: "",
    Prompt: "",
}); err != nil {
    log.Fatalf("Call client.Imagine failed, err: %+v", err)
}
```

[List](#list)

## Features ##

Currently, only some [commands](https://docs.midjourney.com/docs/command-list) have been implemented. All commands will be implemented in the future. If you are interested, please submit a pull request or issues.

- [x] /imagine

- [x] /upscale

- [x] /variation

- [x] /describe

- [ ] /blend

- [ ] /reroll

[List](#list)

## License ##

This library is distributed under the BSD-style license found in the [LICENSE](./LICENSE)
file.

[List](#list)

## Changelog ##

> ## v0.0.1 (20/06/2023)
> - Complete the basic functions
>   * Support for `Imagine` api
>   * Support for `Upscale` api
>   * Support for `Variation` api
>   * Support for `Describe` api

[List](#list)
