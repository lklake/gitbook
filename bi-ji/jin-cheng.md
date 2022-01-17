# 进程

linux内核中，每个taskstruct都有一个pid和tgid。每个进程、线程都有唯一的pid。当新创建一个进程时，这个进程获得一个新的tgid，并且这个进程的线程都为这个tgid。

主线程和子线程的tgid一样。

进程可以堪称一个抽象概念，它是资源分配的基本单位。

线程是一个个任务，调度器调度的是线程。一组线程同属于一个进程。

getpid系统调用实际返回的是tgid，gettid系统调用实际返回的是pid。



还有pgid，是进程组id，几个进程可以组成一个进程组，它们的pgid均为组长的pid。进程组在发信号时有作用。



thread\_pid是一个指针，保存局部id。局部id反映在不同命名空间中的id。



\=======================

findvpid 从当前task的namespace来看，由pid\_​t查找struct pid。

pid namespaces: changes to show virtual ids to user

This is the largest patch in the set. Make all (I hope) the places where\
the pid is shown to or get from user operate on the virtual pids.

The idea is:\
\- all in-kernel data structures must store either struct pid itself\
or the pid's global nr, obtained with pid\_nr() call;\
\- when seeking the task from kernel code with the stored id one\
should use find\_task\_by\_pid() call that works with global pids;\
\- when showing pid's numerical value to the user the virtual one\
should be used, but however when one shows task's pid outside this\
task's namespace the global one is to be used;\
\- when getting the pid from userspace one need to consider this as\
the virtual one and use appropriate task/pid-searching functions.





