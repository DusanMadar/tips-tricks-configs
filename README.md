# Tips-Tricks-Configs

Things which I want to have the same on all machines and I use often but cannot remember or find interesting (worth noting).

1. [Python](#python)
    1. [Generators](#generators)
    2. [Testing](#testing)
2. [Resources](#resources)
    1. [SW Development](#sw-development)

## Python

### Async
* [Python & Async Simplified](https://www.aeracode.org/2018/02/19/python-async-simplified/)

### Debugging
* [Execute multi-line statements within PDB](http://stackoverflow.com/q/5967241/4183498)
  ```python
  (pdb) !import code; code.interact(local=vars())
  ```

### Django
* [Part V – Internationalization and Localization. Languages and Time zones](http://www.marinamele.com/taskbuster-django-tutorial/internationalization-localization-languages-time-zones)
* [Django translation tutorial](http://joaoventura.net/blog/2016/django-translation/)
* [Django site with 2 languages](https://stackoverflow.com/q/10280881/4183498)
* [Getting started with translating a Django Application](https://blog.braham.biz/getting-started-with-translating-a-django-application-d85ec34e505)
* [Solving Performance Problems in the Django ORM](https://medium.com/@hansonkd/performance-problems-in-the-django-orm-1f62b3d04785)

### (virtual)Environment
* [How do you set your pythonpath in an already-created virtualenv?](https://stackoverflow.com/q/4757178/4183498)
  ```
  add2virtualenv /path/to/target/dir
  ```

* [How do I find the location of my Python site-packages directory?](https://stackoverflow.com/q/122327/4183498)
  ```bash
  python -m site
  ```


### Generators
* https://rickardlindberg.me/writing/bitten-by-python-generators/


### Testing
* [Mocking a context manager](http://stackoverflow.com/q/28850070/4183498)
* [Mock yourself, not your tests](http://hernantz.github.io/mock-yourself-not-your-tests.html)
* [Fast Test, Slow Test](https://www.youtube.com/watch?v=RAxiiRPHS9k)
* [Boundaries](https://www.youtube.com/watch?v=eOYal8elnZk)

#### Auto run tests on file change

```bash
find . -name "*.py" | entr python -m unittest discover
```

* [How to automatically run tests when there's any change in my project (Django)?](https://stackoverflow.com/q/15166532/4183498])
* https://github.com/clibs/entr

#### Coverage report
```bash
python -m unittest discover -s tests/
coverage run -m unittest discover -s tests/
coverage report -m --include="*{your_app_name}*"
```


## Resources

Links to resources (tutorials, books, blog posts, repositories, ...).

### SW Development

* https://github.com/jamiebuilds/the-super-tiny-compiler
  * Reading through the guided code will help you learn about how most compilers work from end to end
  
* https://github.com/karan/Projects
  * A list of practical projects that anyone can solve in any programming language
