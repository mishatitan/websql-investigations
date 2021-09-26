# WebSQL Replacement Investigation

## Introduction
> Web SQL Database is a web page API for storing data in databases that can be queried using the SQL variant.

As we know `WebSQL` is deprecated for **Safari** and will be deprecated for **Chrome** in the near future.

###### Release Notes
* Safari: https://developer.apple.com/documentation/safari-release-notes/safari-13-release-notes
* Chrome: https://www.chromestatus.com/feature/5684870116278272

## Description
The **TMA (Technician Mobile App)** uses `WebSQL` for storing data in the *web* and `SQLite` for the *mobile* application. This concept allows the developers to use the same `CRUD` query syntax for `WebSQL` and `SQLite`.

If we reconstruct the `WebSQL` we also have to replace the `SQLite` as the query syntaxes will be different. It will also allow us to rewrite *old* and *ineffective* code that decreases the application speed.

## Alternative Solutions
There are 2 `WebSQL` replacement solutions.
1. [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) - `IndexedDB` is a low-level API for client-side storage of significant amounts of structured data, including files/blobs. This API uses indexes to enable high-performance searches of this data.
    1. Technology status - https://caniuse.com/?search=indexeddb
2. [Web Storage](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) - The `Web Storage API` provides mechanisms by which browsers can store key/value pairs, in a much more intuitive fashion than using cookies.
    1. Technology status - https://caniuse.com/?search=web%20storage

Based on investigations `IndexedDB` is more suitable for our use cases than `Web Storage`. 
For more information please see: [IndexedDB VS Web Storage](https://softwareengineering.stackexchange.com/questions/219953/how-is-localstorage-different-from-indexeddb).

## IndexedDB Libraries/Wrappers
We've investigated the `IndexedDB` to understand its "good" and "bad" sides and to find out the best library that will help us during the development process.
There are a few `IndexedDB` libraries/wrappers that are suitable for us.

### Dexie.js
> **Dexie.js** is a wrapper library for `IndexedDB` - the standard database in the browser.

##### Links:
* Homepage - https://dexie.org/
* GitHub - https://github.com/dfahlander/Dexie.js
* NpmJS - https://www.npmjs.com/package/dexie

| Advantages | Disadvantages |
|:----------:|:-------------:|
| Thinking   | 🤔            |
|            |               |
|            |               |

---

### PouchDB
> **PouchDB** is an open-source JavaScript database inspired by Apache CouchDB that is designed to run well within the browser.

##### Links:
* Homepage - https://pouchdb.com/
* GitHub - https://github.com/pouchdb/pouchdb
* NpmJS - https://www.npmjs.com/package/pouchdb

| Advantages | Disadvantages |
|:----------:|:-------------:|
| Thinking   | 🤔            |
|            |               |
|            |               |

---

### JSStore
> A complete `IndexedDB` wrapper with `SQL` like syntax.

##### Links:
* Homepage - https://jsstore.net/
* GitHub - https://github.com/ujjwalguptaofficial/JsStore
* NpmJS - https://www.npmjs.com/package/jsstore

| Advantages | Disadvantages |
|:----------:|:-------------:|
| Thinking   | 🤔            |
|            |               |
|            |               |

---

### IDB
> This is a tiny (~1.09k brotli'd) library that mostly mirrors the `IndexedDB API`.

##### Links:
* Homepage - https://github.com/jakearchibald/idb#readme
* GitHub - https://github.com/jakearchibald/idb
* NpmJS - https://www.npmjs.com/package/idb

| Advantages | Disadvantages |
|:----------:|:-------------:|
| Thinking   | 🤔            |
|            |               |
|            |               |

---

## Affecting Files
During the migration from `WebSQL/SQLite` to `IndexedDB` listed files will be affected and refactored. (Some files might be missed)

1. **cordova-init-storage.ts**
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/cordova/cordova-init-storage.ts`

1. **database.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/kernel/database.ts`

1. **SQLite.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/cordova/SQLite.ts`

1. **log-sql-storage.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/kernel/log-sql-storage.ts`

1. **state-repository.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/kernel/state-repository.ts`

1. **job-attachment-manager.ts** 
    1. **Description:**  Loading... 🚀
    1. **Path:** `scripts/services/managers/job-attachment-manager.js`

1. **previous-attachment-repository.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/repository/previous-attachment-repository.js`

1. **previous-form-repository.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/repository/previous-form-repository.js`

1. **attachment-table.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/repository/form-data-repository/attachment-table.ts`

1. **picture-table.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/repository/form-data-repository/picture-table.ts`

1. **pricebook-utils.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `scripts/services/utils/pricebook-utils.ts`

1. **database.test.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `tests/mobile/services/kernel/database.test.js`

1. **attachment-table.test.ts** 
    1. **Description:** Loading... 🚀
    1. **Path:** `tests/mobile/services/repository/form-data-repository/attachment-table.test.js`
