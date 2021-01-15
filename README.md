# Go Plugin for Bamboo [![Build Status](https://travis-ci.org/edwinakatosh/go-bamboo-plugin.svg?branch=development)](https://travis-ci.org/edwinakatosh/go-bamboo-plugin)

A plugin for [Atlassian Bamboo](https://www.atlassian.com/software/bamboo) that enables Bamboo to be used as a
Continuous Integration server for [Go](http://golang.org/) projects.

Go Plugin for Bamboo is available on the [Atlassian Marketplace](https://marketplace.atlassian.com):
https://marketplace.atlassian.com/plugins/com.handcraftedbits.bamboo.plugin.go

# Features

* Dependency fetcher task that uses [Godep](https://github.com/tools/godep) to fetch and install project dependencies.
* Test task that executes Go tests and integrates with Bamboo's native test result tracking functionality.
* Build task that builds and installs Go projects.
* Automatic detection of Go-related executables (`go` and `godep`) and `GOROOT` environment variable.

# Installation

Using the Atlassian Marketplace:

1. Log in to your Bamboo server as an administrator.
2. Click the administrator dropdown and choose **Add-ons**.
3. Click **Find new add-ons** from the left-hand side of the page.
4. Search for **Go Plugin for Bamboo**.
5. Click **Install** to download and install.

# Usage

See the [user's guide](doc/guide.md) for information on using the Go Plugin for Bamboo.

# Tutorial

See the [tutorial](doc/tutorial.md) for a step-by-step look at how a Go project can be built and tested with Bamboo.

# TODO

- ~~[ ] Generate [Atlassian Clover](https://www.atlassian.com/software/clover/overview)-formatted code coverage reports
so `go test -cover` can be integrated natively into Bamboo.~~
- [ ] Create a merged `go tool cover -html` output file so all or part of the project's unit tests can be attached as a
build artifact.
- [ ] Support alternative dependency fetchers.
- [ ] Support other Go tools (e.g., `go lint`, `go vet`, `go generate`).

# Building

* Requires Atlassian SDK ([see installation instructions](https://developer.atlassian.com/server/framework/atlassian-sdk/install-the-atlassian-sdk-on-a-linux-or-mac-system/))
* Requires a 1.8 Java SDK. (e.g. [AdoptOpenJDK installed using HomeBrew on macOS](https://github.com/AdoptOpenJDK/homebrew-openjdk)) and `JAVA_HOME` envvar suitably set.
* Run `atlas-package`, which will build a `.jar` in `target/` that can be installed into Bamboo (at `https://bamboo.myCompany.int/plugins/servlet/upm).
