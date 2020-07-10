```python
from dataclasses import dataclass
from typing import Set


class Meta(type):
    def __new__(cls, name, bases, attrs):
        new_cls = super().__new__(cls, name, bases, attrs)
        return dataclass(unsafe_hash=True, frozen=True)(new_cls)


class Bio(metaclass=Meta):
    name        : str = "Redowan Delowar"
    designation : str = "Data Scientist"
    company     : str = "ShopUp"
    base        : str = "Dhaka, Bangladesh"
    blog        : str = "rednafi.github.io/digressions"


class Stack(metaclass=Meta):
    languages   : Set[str] = {"Python", "Go", "Shell"}
    databases   : Set[str] = {"MySQL", "PostgreSQL", "Mongo", "Redis"}
    misc        : Set[str] = {"Docker"}
    ongoing     : Set[str] = {"JavaScript"}


class Social(metaclass=Meta):
    twitter     : str = "rednafi"
    linkedin    : str = "redowan"
```
