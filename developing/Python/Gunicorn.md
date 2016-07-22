# Introduction

Gunicorn 'Green Unicorn' is a Python WSGI HTTP Server for UNIX. It's a pre-fork worker model ported from Ruby's Unicorn project. The Gunicorn server is broadly compatible with various web frameworks, simply implemented, light on server resources, and fairly speedy.

# Basic usage

```
gunicorn [OPTIONS] APP_MODULE
```

Where APP_MODULE is of the pattern $(MODULE_NAME):$(VARIABLE_NAME). The module name can be a full dotted path. The variable name refers to a WSGI callable that should be found in the specified module.

# References

 - [Gunicorn](http://gunicorn.org)