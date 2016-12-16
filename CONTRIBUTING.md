# Helping out with pathmux

### Important

Thanks a lot for your interest in pathmux. Before contributing to it, please consider the following: pathmux is
a fork of httptreemux. Httptreemux is a great and widely known library, and pathmux is only a subset of its
functionality. This means that there is a pretty good chance that more users could benefit from your
improvements, if you contributed them to httptreemux, and ported back to pathmux from there, or the other way
aorund. E.g. in cases when you found a way to improve the performance of the tree lookup. Anyhow you decide,
your contributions are very welcome.

### Ways to contribute

We are happy for any help:

- Report a bug, problem, typo, etc
- (Meta: try to find duplicate bug reports)
- Suggest a feature
- Contribute to the code

Below you can find a few guidelines we would like you to follow. If you need help, please reach out to us:
team-pathfinder@zalando.de.

### Report a bug

Please, do it in any mass, create issues! One nice and responsible way of reporting bugs is to check first if the
same issue was already reported by someone. This prevents splitting the related communication about an issue
into multiple branches. This also means that you are welcome to join any thread, and make comments to existing
issues. If you find an existing issue relevant in any way, without any additional details, you can also use the
GitHub 'reactions' feature to express your opinion.

### Suggest a feature

The same applies here as to the bug reports.

### Contribute to the code

Please, code with us! On this project, we pragmatically but follow the GitHub workflow. The process looks roughly as
the following:

- check the list of open issues. Either assign an existing issue to yourself, or create a new one that you would
  like to work on and discuss your ideas and use cases;
- fork the repository on GitHub;
- check out a topic branch from where you want to base your work; (in simple cases, this is usually master;)
- make sure there are no performance degradations (see below);
- make commits of logical units;
- write good commit messages (see below);
- run `make precommit` (see below);
- push your changes to a topic branch in your fork of the repository; (or if it works for the current state of
  your fork, just use master;)
- submit a pull request to [zalando/pathmux](https://github.com/zalando/pathmux);
- your pull request must receive a :+1: from one [Maintainer](https://github.com/zalando/pathmux/blob/master/MAINTAINERS);

**Before commiting**

Please install the following tools:

- ineffassign: [https://github.com/gordonklaus/ineffassign](https://github.com/gordonklaus/ineffassign)
- misspell: [https://github.com/client9/misspell](https://github.com/client9/misspell)
- golint: [https://github.com/golang/lint](https://github.com/golang/lint)

Please run the following command before commiting:

```
make precommit
```

If it reports any errors, please fix them. (While we don't consider test coverage a real measure of quality,
please rather try to increase it with smart tests than decreasing it.)

**Benchmarking**

Please verify that your changes don't cause any performance degradations (for some projects that use this library,
this is crucial). To get the current performance characteristics, run:

```
make bench
```

Have func and enjoy coding!
