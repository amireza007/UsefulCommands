## Common commands

---
## SQLite c/c++ API

- use this to open `sqlite` db if not created
```c++
sqlite3_open_v2(const char* _filename, sqlite3 ** _db, SQLITE_OPEN_READWRITE | SQLITE_OPEN_CREATE, nullptr);
```
