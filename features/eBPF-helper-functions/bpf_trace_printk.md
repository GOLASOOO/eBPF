# bpf_trace_printk()
It prints a message into the trace log of the kernel.
**Output:** It prints a message like the following one:
```bash
b'      PK-Backend-3305    [000] d..21    83.076264: bpf_trace_printk: Hello World!'
```
Where:
- **b:** means this is a byte String in Python
- **PK-Backend:** the name of the process
- **3305:** PID
- **[000]:** ID of the CPU running the process
- **d..21:** flags
- **83.076264:** timestamp
- **bpf_trace_printk:** event
- **Hello World!** message printed



## Declaration
```c
static long (* const bpf_trace_printk)(const char *fmt, __u32 fmt_size, ...) = (void *) 6;
```

## Return values
- **<0:** Error
- **>=0:** Number of bytes writen

## Usage
Basic usage will require to either:
- Paste the previous definition
- Use external headers that already include such definition, such as ``vmlinux.h`` or ``bpf_helpers.h``.

```c
static const char fmt[] = "Hello, World!"; 
bpf_trace_printk(fmt, sizeof(fmt))
```

Moreover, ``bpf_helpers.h`` provides a macro for ``bpf_trace_printk`` function:
```c
bpf_printk("Hello, World!");
```

