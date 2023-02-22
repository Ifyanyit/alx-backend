# Caching
## General
+ What a caching system is
+ What FIFO means
+ What LIFO means
+ What LRU means
+ What MRU means
+ What LFU means
+ What the purpose of a caching system
+ What limits a caching system have
---
## Requirements
### Python Scripts
+ All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
+ All your files should end with a new line
+ The first line of all your files should be exactly #!/usr/bin/env python3
+ A README.md file, at the root of the folder of the project, is mandatory
+ Your code should use the pycodestyle style (version 2.5)
+ All your files must be executable
+ The length of your files will be tested using wc
+ All your modules should have a documentation (python3 -c 'print(__import__("my_module").__doc__)')
+ All your classes should have a documentation (python3 -c 'print(__import__("my_module").MyClass.__doc__)')
+ All your functions (inside and outside a class) should have a documentation (python3 -c 'print(__import__("my_module").my_function.__doc__)' and python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)')
+ A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)
---

+ 0. **Basic dictionary**<br/>[0-basic_cache.py](0-basic_cache.py) contains a Python class `BasicCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + This caching system doesn't have limit.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ 1. **FIFO caching**<br/>[1-fifo_cache.py](1-fifo_cache.py) contains a Python class `FIFOCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the first item put in cache (FIFO algorithm).
      + You must print `DISCARD: ` with the key discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ 2. **LIFO Caching**<br/>[2-lifo_cache.py](2-lifo_cache.py) contains a Python class `LIFOCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the last item put in cache (LIFO algorithm).
      + You must print `DISCARD: ` with the `key` discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to key.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ 3. **LRU Caching**<br/>[3-lru_cache.py](3-lru_cache.py) contains a Python class `LRUCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the least recently used item (LRU algorithm).
      + You must print `DISCARD: ` with the `key` discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ 4. **MRU Caching**<br/>[4-mru_cache.py](4-mru_cache.py) contains a Python class `MRUCache` that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the most recently used item (MRU algorithm).
      + You must print `DISCARD: ` with the `key` discarded and following by a new line
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.

+ 5. **LFU Caching**<br/>[100-lfu_cache.py](100-lfu_cache.py) contains a Python class LFUCache that inherits from [`BaseCaching`](base_caching.py) and is a caching system:
  + You must use `self.cache_data` - dictionary from the parent class [`BaseCaching`](base_caching.py).
  + You can overload `def __init__(self):` but don't forget to call the parent init: `super().__init__()`.
  + `def put(self, key, item):`:
    + Must assign to the dictionary `self.cache_data` the `item` value for the key `key`.
    + If `key` or `item` is `None`, this method should not do anything.
    + If the number of items in `self.cache_data` is higher than `BaseCaching.MAX_ITEMS`:
      + You must discard the least frequency used item (LFU algorithm).
      + If you find more than 1 item to discard, you must use the LRU algorithm to discard only the least recently used.
      + You must print `DISCARD: ` with the `key` discarded and following by a new line.
  + `def get(self, key):`:
    + Must return the value in `self.cache_data` linked to `key`.
    + If `key` is `None` or if the `key` doesn't exist in `self.cache_data`, return `None`.
