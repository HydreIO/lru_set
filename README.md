# Lru_set

> Basic no-deps Lru Set implementation with timeout support

Add elements in the set and the last used will drop out of it when full.
Elements will also expire and be removed if `max_age` is specified

## 📦 Install

```
npm i @hydre/lru_set
```

## Usage

```js
import Lru from 'lru_set'

const cache = Lru({
  capacity: 5,
  max_age: 100, // if specified, ms before removing an element
  on_eviction: element => { }
})

cache.add(1)
cache.access(5) // returns weither or not an element is still present and also reset his age
```