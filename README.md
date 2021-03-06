# webstorage-utils
Some utils of `WebStorage`

## Install
```
// npm
npm install webstorage-utils

// yarn 
yarn add webstorage-utils

```
## Use
```
import { local, session } from 'webstorage-utils'

local.set('example', 'demo')
local.get('example') // demo

session.set('example', 'demo')
session.get('example') // demo
```

## API
### new WebStorageUtil(options)
- options
  - `storage`: 'localStorage' | 'local' | 'sessionStorage' | 'session'
  - `prefix`: string 

### storage.set(key, value[, ttl])
- `key`: string
- `value`: any
- `ttl`: number, second

```javascript
storage.set('key1', 1)

storage.set('key2', { example: 1 })

// invalid after 10 seconds
storage.set('key3', { example: 1 }, 10)
```

### storage.get(key)
- `key`: string

```javascript
const value1 = storage.set('key1')
```

### storage.del(key)
- `key`: string

```javascript
storage.del('key1')
```

### storage.clear()

```javascript
storage.clear('key1')
```

### storage.updateTTL(key[, ttl])
- `key`: string
- `ttl`: string

```javascript
// refresh original ttl
storage.updateTTL('key1')

// invalid after 10 seconds
storage.updateTTL('key1', 10)
```