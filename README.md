[![PyPI version](https://badge.fury.io/py/plogger.svg)](https://badge.fury.io/py/plogger)
[![Build Status](https://travis-ci.org/c-pher/plogger.svg?branch=master)](https://travis-ci.org/c-pher/plogger)
[![Coverage Status](https://coveralls.io/repos/github/c-pher/plogger/badge.svg?branch=master)](https://coveralls.io/github/c-pher/plogger?branch=master)


## Plogger

Plogger - a simple high level logger wrapper to log into console/file with different level. Used built-in logger module.

## Installation
For most users, the recommended method to install is via pip:
```cmd
pip install plogger
```

## Import
```python
from plogger import Logger
```

## Usage
- As standalone logger:
```python
from plogger import Logger

logger = Logger('test', console=True, file=True)  # Log into file too
logger().info('log this')
logger.logger.info('and log this too')
```

- As part of class using inheritance:
```python
from plogger import Logger

class MyClass(Logger):
    def __init__(self, logger_enabled=True, *args, **kwargs):
        super().__init__(name=self.__class__.__name__, enabled=logger_enabled, *args, **kwargs)
    
    def method_name(self):
        self.logger.info('method_name invoked')
```
