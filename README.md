[![GoDoc](https://godoc.org/github.com/zalando/pathmux?status.svg)](https://godoc.org/github.com/zalando/pathmux)
[![Go Report Card](https://goreportcard.com/badge/github.com/zalando/pathmux)](https://goreportcard.com/report/github.com/zalando/pathmux)
[![Go Cover](https://gocover.io/_badge/github.com/zalando/pathmux)](https://gocover.io/github.com/zalando/pathmux)

# pathmux

Package pathmux implements an effective tree lookup with wildcard matching.

Pathmux is a fork of the awesome [httptreemux](https://github.com/dimfeld/httptreemux). This fork makes the
interface of the internal tree lookup implementation of the original httptreemux package visible, and has the
http related wrapper code stripped off.

In addition to the original httptreemux logic, it offers one small feature: backtracking. This means that when a
path is matched, it is possible to instruct the lookup not to return the found object when other, custom
conditions are not met, but continue the lookup by backtracking from the current point in the tree.

Pathmux is used by Skipper, an extensible HTTP routing server:
[https://github.com/zalando/skipper](https://github.com/zalando/skipper).

### When to use pathmux instead of httptreemux

Almost never, except when:

- you want to store large amount of **custom** objects in an effective lookup tree keyed by path values
- you want to use the backtracking feature to refine the evaluation of wildcard matching with custom logic

### Installation

```
go get github.com/zalando/pathmux
```

Package pathmux is 'go get compatible'. The master head is always stable (at least by intent), and it doesn't
use any vendoring itself. However, we strongly recommend to use vendoring in the final, importing, executable
package.

### Documentation

The package documentation can be found at:

https://godoc.org/github.com/zalando/pathmux

### Working with the code

While it is enough to use `go get` to import the package, when modifying the code, it is worth to cherry-pick
from the tasks in the provided simple Makefile. If you plan to contribute to the current repository, please make
sure:

1. to run the precommit checks:

```
make precommit
```

Please fix all reported errors and please make sure that the overall test coverage is not decreased. (Please
feel free to provide tests for the missing spots :))

2. compare the performance of the new version to the current master, and avoid degradations:

```
make bench
```

(Comparison currently can happen only by running the same `make bench` on the master branch. Automating the
comparison would be a nice contribution.)

Also see our (somewhat) more detailed contribution guildelines:

[https://github.com/zalando/pathmux/blob/master/CONTRIBUTING.md](https://github.com/zalando/pathmux/blob/master/CONTRIBUTING.md)
