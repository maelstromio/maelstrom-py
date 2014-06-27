# Maelstrom [![Build Status](https://travis-ci.org/gradfly/maelstrom.svg?branch=develop)](https://travis-ci.org/gradfly/maelstrom)

A model based database library for Apache Cassandra built on top of DataStax Python Driver. This library has tested support for Python 2.7.

## Installation
Installing through pip is recommended:
```bash
$ pip install py-maelstrom
```
To install the package manually please refer to our installation guide. 

## Get Started
Example usage of Maelstrom:

```python
from uuid import uuid4
from maelstrom.cassandra import connect, close, Base

cassandra.connect([ip1, ip2])

class User(Base):

  __tablename__ = "users"
  
  defaults = {
    'id' = uuid4(),
    'name' = '',
    'email' = '',
  }
  
  lookups = ["email"]
  
  def __init__(self, *args, **kwargs):
    self.update_data(**self.defaults)
    Base.__init__(self, *arks, **kwargs)
    
new_user = User(name = "Joe", email="example@email.com")
new_user.commit()

get_user = Account.get_by_lookup("example@email.com")

cassandra.close()
```

## Documentation
TODO

## License
Copyright 2014 Matt Morse, Joe Peacock and contributors

Maelstrom is licensed under the [MIT License](https://github.com/gradfly/maelstrom/README.md). 
