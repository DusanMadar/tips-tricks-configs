# Tips-Tricks-Configs

Things which I want to have the same on all machines and I use often but cannot remember or find interesting (worth noting).

1. [Python](#python)
    1. [Generators](#generators)
    2. [Testing](#testing)
2. [Resources](#resources)
    1. [SW Development](#sw-development)

## Python

### Generators
* https://rickardlindberg.me/writing/bitten-by-python-generators/


### Testing

#### Auto run tests on file change

```bash
find . -name "*.py" | entr python -m unittest discover
```

* [How to automatically run tests when there's any change in my project (Django)?](https://stackoverflow.com/q/15166532/4183498])
* https://github.com/clibs/entr


## Resources

Links to resources (tutorials, books, blog posts, repositories, ...).

### SW Development

* https://github.com/jamiebuilds/the-super-tiny-compiler
  * Reading through the guided code will help you learn about how most compilers work from end to end
  
* https://github.com/karan/Projects
  * A list of practical projects that anyone can solve in any programming language
