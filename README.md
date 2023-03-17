# os

## Description

A tiny OS layer. This is the API:

```c
#include <stddef.h>

/* Memory */
void* os_memory_alloc(size_t size);
void  os_memory_free(void *ptr);

/* File I/O */
int    os_file_exists(char *file_path);
size_t os_file_size(char *file_path);
size_t os_file_read(char *file_path, void *dest, size_t num_bytes);
size_t os_file_write(char *file_path, void *src, size_t num_bytes);

/* Time */
size_t os_time_now_microseconds(void);

/* Libraries */
typedef void (*os_proc)();
int     os_lib_load(char *name);
os_proc os_proc_get(int os_lib, char *proc_name);
void    os_lib_release(int os_lib);
```

## Usage

Include the library in this way:

```c
#define OS_IMPLEMENTATION_WIN32
#include "os.h"
```

## Supported OS

- [x] Windows
- [ ] Linux
