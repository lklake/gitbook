# 信号

si\_code：indicating why this signal was sent

```c
#define SI_FROMUSER(siptr) ((siptr)->si_code <= 0) 
#define SI_FROMKERNEL(siptr) ((siptr)->si_code > 0)
```

si\_code <=0，表示信号来自用户，使用kill, sigsend, raise发出。

si\_code >0，表示信号来自内核。

值：

任意信号都可以设置：

SI\_USER、SI\_KERNEL、SI\_QUEUE、SI\_TIMER、SI\_MESGQ、SI\_ASYNCIO、SI\_SIGIO、SI\_TKILL

SIGILL信号可以设置设置：

ILL\\\_ILLOPC、ILL\\\_ILLOPN、ILL\\



```
ILL_ILLOPC
```

```
I可以LL_ILLOPC
                  Illegal opcode.

           ILL_ILLOPN
                  Illegal operand.

           ILL_ILLADR
                  Illegal addressing mode.

           ILL_ILLTRP
                  Illegal trap.

           ILL_PRVOPC
                  Privileged opcode.

           ILL_PRVREG
                  Privileged register.

           ILL_COPROC
                  Coprocessor error.

           ILL_BADSTK
```

```
SIGILL
```

