---
content_type: page
description: ''
learning_resource_types:
- Recitations
ocw_type: CourseSection
parent_title: Recitations
parent_type: CourseSection
parent_uid: 08c0c758-213b-77ad-faca-c379a74d5283
title: Recitation 8
uid: c1780287-d0f8-a77d-3b3f-715b457172f9
video_files:
  video_thumbnail_file: null
video_metadata:
  youtube_id: null
---

These notes were prepared by [Petros Komodromos](mailto:komodromos@ucy.ac.cy).  
  
Topics
------------------------------------------------------------------------------------------

1.  **[Exceptions](#1)**
2.  **[Threads](#2)** 
3.  **[I/O](#3)** 
4.  **[Introduction to Java® GUI and Swing](#4)** 

{{< anchor "1" >}}{{< /anchor >}}1\. Exceptions
-----------------------------------------------

Java® provides ways to manage _exceptions_, i.e. errors that may occur during the execution of a program that disrupt the normal flow of instructions. When an unexpected error condition happens during runtime a Java program "_throws_" an exception. This can avoid the premature termination of the program, which in some cases is not necessary. A function that detects an error throws an exception, which can be caught by an _exception handler_. The exception object contains information about the exception, e.g. its type and the state of the program when the error had occurred.

The runtime system tries to find some code to handle the error, i.e. an _exception handler_. The exception causes a search through the call stack to find an appropriate handler to handle the exception. The Java® runtime system searches backwards through the call stack to find any methods that are interested in handling a particular exception. The corresponding, or the default, exception handler catches the exception and may throw a new exception or attempt to handle the exception. If the runtime system, after an exhaustive search of all the methods on the call stack, cannot find an encompassing exception handler the exception is caught by a default exception handler. The latter, usually, prints information about the thrown exception, e.g. where it was thrown, and, then, the runtime system, and, consequently, the Java® program, terminate. An exception handler can catch an exception based on its group or general type by specifying any of the exception's superclasses in the catch statement.

An exception in Java® is an object which is a subclass of the class _Throwable_, and, in most cases, it is derived by the class _Exception_, which is a subclass of _Throwable_. The _Throwable_  class is the superclass of all errors and exceptions in the Java® language. Only objects that are instances of this class, or of one of its subclasses, can be _thrown_ by the Java® VM, or by a Java® _throw_ statement.

In Java®, exceptions are managed by first trying something in a _try{....}_ compound block. The code that might throw an exception is placed in a _try_ block. If an error occurs in that block an exception is thrown. Then, a _catch{.....} block_ is used to catch any exception that is thrown. Zero or more _catch_ blocks may follow the try block. The code that may provide the action that must be taken in the case of a certain exception occurs is provided in a _catch_ block that follows the _try_ block. Each _catch_ block specifies the type of exception it can catch. Only the _Throwable_ class or one of its subclasses can be the argument type in a _catch_ clause. An optional _finally {....}_ block, which follows the last _catch_ block or the try block when there are no _catch_ blocks, provides code that is executed in any case, i.e. regardless whether an exception occurs or not.

**Example**

_class Exceptions1_  
_{_  
 _public static void main(String args\[\])_  
 _{_  
 _double d\[\] = new double\[4\];_  
 _for(int j=0 ; j\<d.length ; j++)_  
 _d\[j\] = j\*7.15 + 2.19 ;_

 _for(int j=0 ; j\<=d.length ; j++)_  
 _{_  
 _try{_  
 _System.out.print( "  d\[" + j + "\] / " + j + " = ");_  
 _if(j==0)_  
 _& #160;  throw new DivideByZeroException();_  
 _System.out.println(d\[j\]/j);_  
 _}_  
 _catch(ArrayIndexOutOfBoundsException e)_  
 _{_  
 _System.out.println("Exception: " + e.getMessage());_  
 _System.out.print("e.printStackTrace(): ");_  
 _e.printStackTrace();_  
 _}_  
 _catch(DivideByZeroException e)_  
 _{_  
 _System.out.println("Exception: " + e.getMessage());_  
 _}_  
 _finally_  
 _{_  
 _System.out.println("Inside finally()\\n");_  
 _}_  
 _}_

 _System.out.println( "\\n  Program exiting \\n");_  
 _}_  
_}_

_class DivideByZeroException extends ArithmeticException_  
_{_  
 _DivideByZeroException()_  
 _{_  
 _super("Trying to divide by zero");_  
 _}_  
_}_  
 

**_Output:_**

 _d\[0\] / 0 = Exception: Trying to divide by zero_  
_Inside finally()_

 _d\[1\] / 1 = 9.34_  
_Inside finally()_

 _d\[2\] / 2 = 8.245000000000001_  
_Inside finally()_

 _d\[3\] / 3 = 7.880000000000002_  
_Inside finally()_

 _d\[4\] / 4 = Exception: null_  
_e.printStackTrace(): java.lang.ArrayIndexOutOfBoundsException_  
 _at Exceptions1.main(Compiled Code)_  
_Inside finally()_

 _Program exiting_  
 

A _checked exception_ requires the specification of the way that the exception should be handled. If a function may result in a _checked exception_, this must be defined using the keyword _throws_ at the definition of the class, after its name. A method can only throw checked exceptions that have been specified in its declaration. Java® requires that a method should either catch, or specify all checked exceptions that can be thrown within the scope of that method.

_Unchecked exceptions_ are of type _RuntimeException_, _Error_, or subclasses of them, and can be thrown anywhere without the need to specify the possibility of such exceptions to be thrown. Classes _Exception_ and _Error_ are subclasses of the class _Throwable__,_ as shown in the following figure, which was adapted from Sun's Java® Tutorial. Class _RuntimeException_ is a subclass of the class _Exception_.

{{< resource "f494f101-342f-990d-5567-57018b331777" >}}

Any method (i.e. function) that may produce a non-RuntimeException should declare the type of exception that it can produce using the _throws_ keyword, or that exception should be caught in a _try/catch_ block in the method. The basic error type is class _Exception_, although there are more specific types of exceptions. When a checked exception occurs, the _throw_ keyword may used to actually create the _Exception_ object and either an exception handler should catch and handle the exception, or the function exits. Java® uses the "termination model of exception", since control cannot return to the _throw point,_ when an exception is thrown.

Code that may produce an exception is placed within the try block of a _try-catch_ statement. If the code within the _try_ block fails, the code within a corresponding _catch_ block, if exists, is executed. When an exception is thrown the control goes out of the _try_ block and searches the _catch_ blocks to find an appropriate handler. If the code succeeds, then control passes to the next statement following the _try-catch_ statement or to the finally block. In the presence of a _finally_ block, the latter is also executed irrespectively of whether an exception has occurred. If no exception handler is found for an exception, the search continues in the enclosing try block and a Java® application terminates if no exception handler is eventually found.

Class _Error_  is, also, provided in Java® to be used for serious problems that should not be caught. The _Error_ class is a subclass of the _Throwable_ class. _RuntimeExceptions_ should be dealt directly rather than throw an exception.

The main advantages of using exception handling are that regular code is separated from error handling code making the code much more readable. Also, error types can be grouped together, and the errors can propagate up the call stack to find a proper exception handler.

However, use of exception handling for purposes other than error handling should be avoided since it can cause a performance overhead. Exception handling should be used only when a method is unable to detect and process an error and, thus, it throws an exception under an exceptional situation, instead of processing it locally. You should avoid using exception-handling for purposes other than error handling. The latter reduces clarity but also results in an execution time overhead imposed by the exception handling code. However, when an exception does not occur there is almost no execution overhead.

An exception handler can do several things such as try to recover and resume execution, rethrow an exception, throw a different type of exception. As soon as the exception handler begins execution the _try_ block has expired, and control is in a different scope. If an exception occurs in a handler, it may be processed only by code outside the _try_ block in which the original exception had been thrown. Similarly, a rethrown exception can be caught only by an exception handler after the next enclosing _try_ block.

A subclass class overridden method can have in its _throws list_ only the same with, or a subset of, its superclass's method throws list.

{{< anchor "2" >}}{{< /anchor >}}2\. Threads
--------------------------------------------

A _threat_ is a single sequence of steps executed one at a time, i.e. a sequential flow of control, running within a program and taking advantage of the resources allocated for that program and its environment.

_Multithreading_ allows to a program to perform several tasks, i.e. to use more than one flow of control, concurrently. All threads of a multithreading Java® program share the same data and system resources, running at the same time and performing different tasks. Since most computers have only one CPU, threads share the CPU with other threads.

Threats can be used by one of the following ways:

By providing a subclass of the _Thread_ class

By providing a class that implements the _Runnable_ interface.

  
 1. Providing a subclass of the _Thread_ class:

We need to provide a subclass of the _Thread_ class. This subclass should override the _run()_ method of class _Thread_. The latter must contain all code that is to be executed within the thread. An instance of the subclass can then be allocated and started.

_class MyThreadClass extends Thread_  
_{_

 _public void run()_  
 _{_  
 _// Code to be executed within the thread_  
 _}_

_}_  
 

Then, we can create a new thread by instantiating a subclass of the _Thread_ class. Then, we can configure the thread, e.g. by setting its initial priority, name, etc. Finally, we can run it, by calling the _start()_ method that is inherited from the class _Thread,_ which invokes the new thread's _run()_ method.

> _MyThreadClass x = new MyThreadClass();_  
> _x.start();_

However, using this approach is not possible when we need to extend some other class, since Java® does not allow multiple inheritance.

**Example**

_class MyThreadClass extends Thread_  
_{_  
 _String name;_

 _MyThreadClass(String str)_  
 _{_  
 _name = str;_  
 _}_

 _public void run()_  
 _{_  
 _for(int i=0; i\<5;i++)_  
 _{_  
 _System.out.println("Thread: " + name);_  
 _try_  
 _{_  
 _Thread.sleep((int) (Math.random()\*1000));_  
 _}_  
 _catch(InterruptedException e)_  
 _{_  
 _System.out.println("Catch: " + getName());_  
 _}_  
 _}_  
 _}_

_}_

_class ThreadExample1_  
_{_  
 _public static void main(String args\[\])_  
 _{_  
 _MyThreadClass  th1 = new MyThreadClass("Thread-1");_  
 _MyThreadClass  th2 = new MyThreadClass("Thread-2");_  
 _MyThreadClass  th3 = new MyThreadClass("Thread-3");_  
 

 _th3.start();_  
 _th1.start();_  
 _th2.start();_

 _}_  
_}_

_Output: _   > java ThreadExample1

> _Thread: Thread-3_  
> _Thread: Thread-1_  
> _Thread: Thread-2_  
> _Thread: Thread-1_  
> _Thread: Thread-1_  
> _Thread: Thread-3_  
> _Thread: Thread-1_  
> _Thread: Thread-2_  
> _Thread: Thread-3_  
> _Thread: Thread-1_  
> _Thread: Thread-3_  
> _Thread: Thread-2_  
> _Thread: Thread-3_  
> _Thread: Thread-2_  
> _Thread: Thread-2_

  
2\. Implementing the Runnable Interface

The other way to create a thread is to declare a class that implements the _Runnable_ interface. The _Runnable_ interface requires the implementation of the _run()_ method, in which all code that is to be executed within the thread should be placed. An instance of the class can then be allocated. Finally, a _Thread_ object can be created passing as an argument the object of the class that implements the _Runnable_ interface, and, then start the thread.

_class MyRunnableClass implements Runnable_  
_{_

 _public void run()_  
 _{_  
 _//  Code to be executed within the thread_  
 _}_

_}_

A new thread can by created by creating a _Thread_ object using an object of type _MyRunnableClass_, and, then, by calling the _start()_ method, of the _Threat_ class, which runs the thread.

> _MyRunnableClass x = new MyRunnableClass();_  
> _Thread t = new Thread(x);_  
> _t.start();_

**Example**

_class MyRunnableClass implements Runnable_  
_{_  
 _String name;_

 _MyRunnableClass(String str)_  
 _{_  
 _name = str;_  
 _}_

 _public void run()_  
 _{_  
 _for(int i=0; i\<5;i++)_  
 _{_  
 _System.out.println("Thread: " + name);_  
 _try_  
 _{_  
 _Thread.sleep((int) (Math.random()\*1000));_  
 _}_  
 _catch(InterruptedException e)_  
 _{_  
 _System.out.println("InterruptedException in " + name + " thread.");_  
 _}_  
 _}_  
 _}_

_}_

_class ThreadExample2_  
_{_  
 _public static void main(String args\[\])_  
 _{_  
 _MyRunnableClass  r1 = new MyRunnableClass("Thread-1");_  
 _MyRunnableClass  r2 = new MyRunnableClass("Thread-2");_  
 _MyRunnableClass  r3 = new MyRunnableClass("Thread-3");_

 _Thread th1 = new Thread(r1);_  
 _Thread th2 = new Thread(r2);_  
 _Thread th3 = new Thread(r3);_

 _th3.start();_  
 _th1.start();_  
 _th2.start();_

 _}_  
_}_  
 

_Output:_      > java ThreadExample2

> _Thread: Thread-3_  
> _Thread: Thread-1_  
> _Thread: Thread-2_  
> _Thread: Thread-2_  
> _Thread: Thread-2_  
> _Thread: Thread-1_  
> _Thread: Thread-3_  
> _Thread: Thread-2_  
> _Thread: Thread-3_  
> _Thread: Thread-2_  
> _Thread: Thread-1_  
> _Thread: Thread-1_  
> _Thread: Thread-3_  
> _Thread: Thread-3_  
> _Thread: Thread-1_

States of a thread during its lifetime:

_New_: A new thread is one that has been created, i.e. using the new operator, but has not yet been started.

_Runnable (ready state)_: A thread becomes runnable once its _start()_ method has been invoked, which means that the code in the _run()_ method can execute whenever the thread receives CPU time from the operating system. A threat that had been set to sleep and the time interval has expired, a thread which was waiting and has been notified, a thread that had been suspended and it has been resumed, and a thread that had been blocked by an I/O request and the I/O has been completed are also in a runnable state.

_Not Runnable (blocked state)_: A thread can become not runnable if: the thread's _sleep()_ method is invoked (in which case, the thread remains blocked for a specified number of milliseconds, giving a chance to lower-priority threads to run); the thread's _suspend()_ method is invoked (in which case, the thread remains blocked until its _resume()_ method is invoked); the thread calls the _wait()_ method of an object (in which case, the thread remains blocked until either the object's _notify()_ method or its _notifyAll()_ method is called from another thread); the thread has blocked on an I/O operation (in which case the thread remains blocked until the I/O operation has been completed)

_Dead_: A thread can die either because the _run()_ method has finished executing, i.e. has terminated, or because the thread's _stop()_ method has been called. The latter should be avoided because it throws a _ThreadDeath_ which is a subclass of _Error_.

The following diagram shows the possible life cycle of a thread:

{{< resource "ae8a01ce-c067-8292-35c5-26a24e75c1e2" >}}

Note that the methods _stop(), suspend()_, and _resume()_ have been _deprecated_, and, therefore, should be avoided to manage threads. Instead of using the _stop()_ method, someone can modify some variable to indicate that the target thread should stop running. The target thread should check this variable regularly, and return from its run method as soon as this variable indicates that it is to stop running. A variable indicating the desired state of the thread can be used to specify whether it should be active or suspended, in order to avoid the _suspend()_, and _resume()_ methods. When the desired state is suspended, the thread can wait using the _wait()_ method. When the thread is resumed, the target thread is notified using the _notify()_ method.

The _wait_() method makes a thread wait until some condition is satisfied. Actually _wait()_ not only pauses the corresponding tread but also releases the lock on the object, which allows other threads to invoke synchronized code on that object. The notification methods _notify_() and _notifyAll_() can be used to inform waiting threads that there was some change that might have caused the satisfaction of that condition. Almost always the _notifyAll_() method is used to wake up all waiting threads, while _notify_() picks one of the waiting threads and wakes it up. Notifications affect only threads that have been waiting ahead of the notification, i.e. the _wait_() has been executed before the occurrence of the notification. The wait and notify methods can be invoked only from _synchronized_ code, either directly or indirectly (through another method called from the _synchronized_ code).

Typically _wait()_ is used as follows. Note that the condition test should always be in a loop.

> _synchronized  returnType functionName()_  
>  _{_  
>  _while(!condition)_  
>  _wait();_  
>  _statements to be executed when the condition is true_  
>  _notifyAll();_  
>  _}_

  
The normal and cleanest way to end a thread's life is having the _run()_ method return.

Method _interrupt_() can be used to interrupt a thread execution.

Every thread has a _priority,_ which is a number between _Thread.MIN\_Priority_ and _Thread.MAX\_Priority_. Threads with higher priority are executed in preference to threads with lower priority. When code running in some thread creates a new _Thread_ object, the new thread has its priority initially set equal to the priority of the creating thread.

When multiple threads are runnable (i.e. ready to be executed), the runtime system chooses the runnable thread with the highest priority for execution. Only when that thread stops, yields, or becomes not runnable for some reason a lower priority thread will start executing.

Java® platforms that support time-slicing allow each thread of equal priority to run by providing to all threads a limited amount of the processor's time. On Java® platforms that do not support time-slicing a thread of a given priority runs to completion or until a higher (but not equal) priority thread becomes runnable. Method _yield_(), which is useful only on non-time-slicing systems, allows threads of the same priority to run.

Execution of multiple threads in some order is called _scheduling_. This is supported by  a very simple, deterministic scheduling algorithm (fixed priority scheduling) of the Java® runtime. This algorithm schedules threads based on their priority relative to other runnable threads. The Java® scheduler keeps the highest priority thread running at all times, and when time-slicing is supported allows equal high-priority threads to execute by giving slices of the processor time to them in sequence. In general, it is good practice to have the continuously running part of a program, or  threads that do frequent and continual updates set to MIN\_PRIORITY to avoid blocking other threads.

Threads on multiprocessor machines utilize the multiple processors. A number of the highest-priority threads equal to the number of the available processors execute.

Someone can set and get the name of a threat using the functions _setName()_ and _getName()_, respectively, of the _Threat_ class. The priority can be set and got using the methods set and get methods of the _Thread_ class.

The thread object of the currently running thread can be obtained using the _currentThread()_ method of the _Thread_ class.

**Example**

_class MyRunnableClass implements Runnable_  
_{_  
 _String name;_

 _MyRunnableClass(String str)_  
 _{_  
 _name = str;_  
 _}_

 _public void run()_  
 _{_  
 _for(int i=0; i\<5;i++)_  
 _{_  
 _System.out.println("Thread: " + name);_  
 _try_  
 _{_  
 _Thread.sleep((int) (Math.random()\*3));_  
 _}_  
 _catch(InterruptedException e)_  
 _{_  
 _System.out.println("InterruptedException in " + name + " thread.");_  
 _}_  
 _}_  
 _}_

_}_

_class ThreadExample3_  
_{_  
 _public static void main(String args\[\])_  
 _{_  
 _MyRunnableClass  r1 = new MyRunnableClass("Thread-1");_  
 _MyRunnableClass  r2 = new MyRunnableClass("Thread-2");_  
 _MyRunnableClass  r3 = new MyRunnableClass("Thread-3");_

 _Thread th1 = new Thread(r1);_  
 _Thread th2 = new Thread(r2);_  
 _Thread th3 = new Thread(r3);_

 _th2.setPriority(10);_  
 _th3.setPriority(1);_

 _System.out.println(" th1 priority: " + th1.getPriority());_  
 _System.out.println(" th2 priority: " + th2.getPriority());_  
 _System.out.println(" th3 priority: " + th3.getPriority() + "\\n");_

 _th3.start();_  
 _th1.start();_  
 _th2.start();_

 _}_  
_}_

_Output:_     > java ThreadExample3

>  _th1 priority: 5_  
>  _th2 priority: 10_  
>  _th3 priority: 1_
> 
> > _Thread: Thread-2_  
> > _Thread: Thread-2_  
> > _Thread: Thread-2_  
> > _Thread: Thread-2_  
> > _Thread: Thread-2_  
> > _Thread: Thread-1_  
> > _Thread: Thread-1_  
> > _Thread: Thread-1_  
> > _Thread: Thread-3_  
> > _Thread: Thread-1_  
> > _Thread: Thread-1_  
> > _Thread: Thread-3_  
> > _Thread: Thread-3_  
> > _Thread: Thread-3_  
> > _Thread: Thread-3_

Java®'s garbage collector runs as a low-priority thread when processor time is available and when there are no higher-priority runnable threads.

Each thread may or may not be marked as a _daemon_. A daemon thread is a thread that runs in the background (when the processor is available) for the benefit of other threads. An example of a daemon thread is the garbage collector. When code running in some thread creates a new _Thread_ object, the new thread is a _daemon_ thread if and only if the creating thread is a _daemon_. Daemon threads do not prevent a program from terminating, since the program exits when only daemon threads remain in it. The Java® VM exits when the only threads running are all daemon threads. The function _setDaemon(boolean on)_ can be used, before the thread is started, to mark a thread as a daemon thread or a user thread. If the argument to the _setDaemon(boolean on)_ is true, the thread is marked as a daemon thread.

A s_elfish thread_ is a thread that never voluntarily gives up the control of the CPU, continuing running until either the thread's run() method terminates, or until the thread is preempted by a higher priority thread. Time-slicing systems do not allow to a selfish thread to keep the control when there are other multiple runnable threads of equal priority, allowing the other threads to run.

In particular, someone should never rely on time-sharing and should write well behaved threads that periodically give up, voluntarily, the control of the CPU, giving to other threads an opportunity to run.

_Race hazard_, or _race condition_, is the situation in which two or more threads can modify the same data in a way that the data can be corrupted by inconsistent changes.

_Starvation_ is an indefinite postponement of the execution of lower-priority threads due to higher-priority threads which do not give them the chance to run. Starvation occurs when one (or more threads) in a program cannot progress because it is blocked from gaining access to a certain resource.

_Deadlock_ is the worst case of starvation, which occurs when two or more threads are waiting on a condition that cannot be satisfied, e.g. when two (or more) threads are each waiting for the action of the other(s). Race conditions can arise from multiple, asynchronously executing threads that are trying to access a single object (data) at the same time which may result on a wrong result and inconsistencies. Synchronization can be used to avoid such race problems.

When several concurrent threads are competing for resources, _starvation_ and _deadlock_ should be prevented. Each thread should get enough access to limited resource in order to reasonably progress without causing problems to the other threads or corrupting common data.

_Synchronization_

In some cases separate, concurrently running threads share data in a way that they must take into account the state of other threads. An example of such a case is the so-called _producer/consumer_ scenario in which the "producer" thread generates data that are consumed by a "consumer" thread.

In such cases, problems can be avoided using _synchronization,_ which allows a thread to lock an object and in case of another thread trying to invoke a synchronized method on the same object, the second thread will be blocked until the object is unlocked from the first thread. A lock is associated with every object that has _synchronized code_.

_Critical code sections_ are code segments (e.g. a method) within a program that access the same data (e.g. object) from separate but concurrent threads. In the Java® language, the _synchronized_ keyword is used to identify a critical section. Whenever a synchronized method of a class is invoked, the associated object is locked by that method. A synchronized method cannot be called on the same object until the object is unlocked, i.e. another thread cannot invoke a _synchronized_ method on that object until the lock is released. When a synchronized method is invoked on an object it obtains its lock, not allowing any other thread to invoke any synchronized method until it releases the lock. A thread can voluntarily call _wait()_, which releases the lock and the processor, and wait in a queue while other threads are able to obtain the lock and invoke _synchronized_ code. The methods _notify_() and _notifyAll()_  can be used to signal to waiting threads to become ready again and attempt to obtain the lock. If waiting threads are not notified the threads will wait forever causing a deadlock.

Java® locks are _reentrant_, i.e. it is allowed to a thread to re-acquire a lock that it already holds. This avoids problems in which arise when a thread calls from a synchronized method of an object another synchronized method of the same object, which could lead into deadlock.

Static methods can also be _synchronized_. In that case a "class lock" for the corresponding class is used, which does not allow two threads to execute _synchronized_ static methods on the same class at the same time.

A _synchronized statement_ is an alternative, in some cases, way to execute synchronized code that locks the object so that no _synchronized_ method can be invoked on that object, since it is locked.  
 

>  _synchronized(objectTobeLocked)_  
>  _{_  
>  _statements_  
>  _}_

Thread Group
------------

In Java® every Thread object is a member of a thread group, which allows to handle multiple threads, which belong in the same thread group, as a group. The _ThreadGroup_ class is used to implement thread groups and allow to deal with the threads in a thread group as a group.

The Java® runtime system creates a ThreadGroup by default, named _main_, as soon as a Java® application starts. A newly created thread is placed in the same group with the thread group in which the thread that created it belongs. Therefore, unless specified otherwise, all new threads that are created become members of the main thread group by default. In an applet a newly created thread may belong to some other than main thread group depending on the browser. A thread cannot change thread group after its creation.

A _ThreadGroup_  can contain any number of threads, which usually, however, are related in some way, and even other ThreadGroup objects. The top-most ThreadGroup in a Java® application is the ThreadGroup named _main_, which is the default thread group.

Method _activeCount_() gives the number of active threads in a thread group plus those in all its child thread groups. The _ThreadGroup_ class provides a variety of methods to manage, and operate _ThreadGroup_ objects and the _Thread_ objects that are members of those thread groups.  
 

 {{< anchor "3" >}}{{< /anchor >}} 3. I/O
-----------------------------------------

The **_System_** class, which is a final class and has private constructors (i.e. not allowing its extension), provides several useful class variables and methods. For example _System.out_ is a _PrintStream_ object that implements the standard output stream, and _System.getProperty(String key)_ is a static method that returns the system property indicated by the specified key.

The **_System_** class provides:

*   _in_: the standard input stream to read input data (static _InputStream_ object)
*   _out_: the standard output stream to output results (static _PrintStream_ object)
*   _err_: the standard error stream to display error messages (static _PrintStream_ object)

Both standard output and error, which are derived from the _PrintStream_ class, can invoke one of the _PrintStream's_ methods _print()_, _println()_, and _write()_ to print text to the stream. The latter method, which is not that common is used to write non-ASCII data, i.e. to write bytes to the stream.

The _java_.io package provides a collection of stream classes that support reading from and writing to an external destination. The provided classes operate on either characters or byte data types.  
  
The abstract superclasses for character streams in _java_.io are the _Reader_ (abstract class for reading character streams) and the _Writer_ (abstract class for writing to character streams) classes, which partially provide the functionality for the characters reader and writer stream classes, respectively. _\[The following inserted figures have been adapted from the on-line [Java® Tutorial](http://java.sun.com/docs/books/tutorial/) of SUN\]_

{{< resource "1cbba491-40a5-7fb2-5b61-8b2b09f8ad7f" >}}

{{< resource "dbddd749-9bde-d555-8b04-5f94dcea773b" >}}

In general, readers and writers should be preferred to read and write information since they can handle any character in the Unicode character set because they use 16-bits per character.

Similarly, the abstract superclasses for byte streams in _java.io_ are the _InputStream_ (abstract class for reading byte streams) and the _OutputStream_ (abstract class for writing to byte streams) classes.

{{< resource "1cbac8d9-2fb4-22ad-4bce-f2b8e530b55c" >}}

{{< resource "3aa45619-1b51-aac0-7185-03a7d52afeed" >}}

_Reader_ and _InputStream_ provide methods for reading characters and bytes, respectively. They also provide methods for marking a location in the stream, skipping input, and resetting the current position. Similarly, _Writer_ and _OutputStream_ provide methods for writing characters and bytes, respectively.

All readers, input streams, writers, and output streams are automatically opened upon the creation of the corresponding objects. Although they are eligible to be closed by the garbage collector, as soon as they are not referenced in any way, they can be explicitly closed by calling their _close()_ method.

The above stream classes can be categorized into two groups: one that deals with reading and writing data, and another that performs some kind of operation on the data while reading and writing. The former are the ones shown with gray color in the above figures, while the latter are the ones shown in white.

A useful class provided by the _java.io_ package is the _StreamTokenizer_ class. A _StreamTokenizer_ object can be created using as argument to its constructor call an _InputStreamReader_ object. Then, the _StreamTokenizer_ object may be used on an input stream to parses it into tokens, which it reads one at a time.

 {{< anchor "4" >}}{{< /anchor >}} [4\. Introduction to Java® GUI and Swing](http://java.sun.com/docs/books/tutorial/uiswing/TOC.html)
--------------------------------------------------------------------------------------------------------------------------------------

_[Java® Foundation Classes](http://java.sun.com/products/jfc/index.html)[(JFC)](http://java.sun.com/products/jfc/index.html)_ provide features to facilitate the development of Graphical User Interfaces (_GUI_s). Among other, JFC provides _**Swing**__**,**_ which includes several [components](http://www.javadesktop.org/rollups/components/) that can be used for the development of GUIs, support for a choice on the look and feel that a program uses, and provides [_Java®2D_](http://java.sun.com/docs/books/tutorial/2d/index.html) for high quality 2D graphics. Finally, swing allows the specification which look and feel a program should use. This is done with the _setLookAndFeel()_ method of the _UIManager_ class. _**Swing**_ is built on top of the _AWT_ (Abstract Window Toolkit) using the AWT infrastructure. However, **_Swing_** provides its own graphical user interface (GUI) components, many of which have a close relation or correspondence to the _AWT_ components. Essentially, **_Swing_** is an extension and improvement to the _AWT_.

JFC 1.1 (with Swing API 1.1) is built into _JDK 1.2__._ The latest JFC development is the JFC/Swing portion of JDK 1.3, which is code-named _Kestrel_ and it was released this year.

The Swing API is provided in the following Swing packages:

*    _javax.swing_   (the main swing package)
*    _javax.swing.border_
*    _javax.swing.colorchooser_
*    _javax.swing.event_
*    _javax.swing.filechooser_
*    _javax.swing.plaf_
*    _javax.swing.plaf.basic_
*    _javax.swing.plaf.metal_
*    _javax.swing.plaf.multi_
*    _javax.swing.table_
*    _javax.swing.text_
*    _javax.swing.text.html_
*    _javax.swing.text.html.parser_
*    _javax.swing.text.rtf_
*    _javax.swing.tree_
*    _javax.swing.undo_

The _AWT_ (Abstract Window Toolkit) was first used to develop GUI's in Java®, and provided the foundation on which the JFC and swing were built. The main difference between _AWT_ and _Swing_ is that the components of the latter are implemented without any native code. Because of this, swing components are called lightweight, while AWT components, which use native code, are called heavyweight components. Lightweight components are drawn entirely using Java®, while heavyweight components use native peers. Actually, _AWT_ 1.1 also introduced some lightweight components, while earlier versions were based solely on heavyweight components. _Swing_ components, in general, have much more capabilities than the AWT corresponding ones. For instance some Swing components (such as labels and buttons) can display icons, while the corresponding AWT components cannot. _Swing_ provides a number of additional components that were not provided by AWT.

_Swing_ provides several standard components (e.g. buttons, checkbuttons, radiobuttons, menus, lists, labels, and text areas) to create a program's GUI using one or more containers (e.g. frames, dialogs, windows and tool bars). Most Swing components that begin with J, except the top-level containers, are subclasses of the _JComponent_ class. The letter J is used to differentiate the actual extra user interface classes provided by Swing from the support classes that it provides. Swing components inherit many features from the _JComponent_ class, such as a configurable look and feel, borders, and tool tips, as well as many methods. In addition, some Swing components can display images on them. The _JComponent_ class extends the _Container_ class (provides support for adding and laying out components), which itself extends the _Component_ class (provides support for  painting, events, layout etc.). _JComponent_ is the base class for almost all lightweight J components. Therefore, all swing lightweight components (derived from the _JComponent_ class) are subclasses of the _Container_ class of _AWT_.

The following article, by Bill Harlan, provides some useful information about [**_Improving Swing Performance._**](http://www.billharlan.com/papers/Improving_Swing_Performance.html)

Containers
----------

Every program with a _Swing_ GUI contains at least one top-level Swing container, i.e., in general, an instance of a _JApplet_, _JFrame_, or _JDialog_, which enables the painting and event handling of the Swing components. The _JApplet_, _JFrame_, or _JDialog_, are considered top-level containers because they are used to provide an area in which the other containers and components can appear. Other containers, such as the _JPanel_, are used to facilitate the positioning and sizing of other containers and components. Between a top-level container and an intermediate container, a content pane (_JRootPane_), which is also an intermediate container, is indirectly provided. The content pane contains all of visible components of its GUI, except a menu bar. One of the _add()_ methods of a container can be used to add a component to it. The component to be added is used as argument to the add method. In some cases another argument, which has to do with the layout, is used with the _add()_ method.

Besides the _top-level_ containers (_JApplet_, _JFrame_, _JDialog_, and _JWindow)_ there are _special-purpose_ containers (such as the _JInternalFrame_, _JLayeredPane_, and _JRootPane_) that are used for special purposes, and _general-purpose_ containers (such as _JPanel_, _JScroll Pane_, _JSplitPane_, _JTabbedPane_, and _JToolBar_) that are used for other any general purpose.

The _JApplet_ and _JFrame_ classes should be used to implement Swing applets or applications, respectively. Both _JApplet_ and _JFrame_ classes are containers that contain an instance of the _JRootPane_ class. The latter contains the content pane, which is a container, that contains all the components contained in the applet or application. Therefore, components should be added and layout managers should be set to the content pane.

Atomic Components
-----------------

There are many atomic components (i.e. components that exist as self-sufficient entities and not to hold other Swing components). Atomic components can be grouped into 3 categories:

*   _Basic Controls_, which are components that can primarily be used to get input from the user (such as _JSlider__, _ _JTextField__, _ _JButton__, _ _JComboBox__, _ _JList__,_ and _JMenu_)
*   _Uneditable Information Displays,_ which are used to display information to the user (such as _JProgressBar_, _JLabel__,_and _JToolTip_)
*   _Editable Displays of Formatted Information_, which are components that can be used to display formatted information that can be editable by the user (such as _JColorChooser__, _ _JTextComponent__, _ _JFileChooser__, _ _JTable_, and _JTree_)

Applets and Applications
------------------------

_Swing applets_ use the _JApplet_ class which is a subclass of the _AWT_  _Applet_ class and implements the _Accessible_ and _RootPaneContainer_ interfaces. The following simple example shows an applet with a single component a _JLabel__._ The _BorderLayout_ manager is used by the _JApplet_ for its content pane (which is used in both Swing applets and applications), in contrast to the _FlowLayout_ manager used by the _Applet_ class.  
 

> SwingApplet1.java

> _import java.awt.\*;_  
> _import javax.swing.\*;_
> 
> _public class SwingApplet1 extends JApplet_  
> _{_  
>  _public void init()_  
>  _{_  
>  _Icon icon = new ImageIcon("1.124.gif", "1.124 GIF");_  
>  _JLabel label = new JLabel(" Test", icon, SwingConstants.CENTER);_  
>  _getContentPane().add(label);_  
>  _}_  
> _}_

  
The above applet can be executed using an html file like the following:

> SwingApplet1.html

> _\<html>_  
> _\<head>_  
>  _\<title>JApplet Example # 1\</title>_  
> _\</head>_  
> _\<body>_
> 
> _\<center>_  
> _\<h2>_  
> _\<u>JApplet Example # 1\</u>\</h2>_  
> _\<hr>\<applet code="SwingApplet1.class" WIDTH="486" HEIGHT="94">\</applet>_  
> _\<hr>\</center>_
> 
> _\<p>\<br>_  
> _\</body>_  
> _\</html>_

Then, appletviewer (using the command: _appletviewer SwingApplet1.html_) displays the following window:

{{< resource "e2e07bc1-49a4-0f71-39ec-550361e33d5d" >}}

Similarly, the _JFrame_ class can be used to create a _Swing application_ similar to the above applet. The _JFrame_ class is a subclass of the _AWT_   _Frame_ class and implements the _Accessible__,_ _WindowConstants__,_ and _RootPaneContainer_ interfaces. It uses the _BorderLayout_ manager for its content pane. The source code is presented below:

> SwingApplication1.java

> _import java.awt.\*;_  
> _import javax.swing.\*;_  
> _import java.awt.event.\*;_
> 
> _public class SwingApplication1 extends JFrame_  
> _{_
> 
>  _public SwingApplication1()_  
>  _{_  
>  _super("Swing Application");_  
>  _Icon icon = new ImageIcon("1.124.gif", "1.124 GIF");_  
>  _JLabel label = new JLabel(" Test", icon, SwingConstants.CENTER);_  
>  _getContentPane().add(label);_  
>  _}_  
>  
> 
>  _public static void main(String args\[\])_  
>  _{_  
>  _final JFrame jfr = new SwingApplication1();_
> 
>  _jfr.setBounds(100,50,500,150);_  
>  _jfr.setVisible(true);_
> 
>  _jfr.setDefaultCloseOperation(DISPOSE\_ON\_CLOSE);_
> 
>  _jfr.addWindowListener(new WindowAdapter()_  
>  _& #160;       {_  
>  _& #160;              public void windowClosed(WindowEvent e)_  
>  _& #160;                   {_  
>  _& #160;                     ; System.exit(0);_  
>  _& #160;                   }_  
>  _& #160;            }              );_  
>  _}_
> 
> _}_

As any Java® application, a _main()_ method must be provided. In _main()_ a _JFrame_ is instantiated, sized, and made visible. The default close operation is set to _DISPOSE\_ON\_CLOSE_ (to dispose any native resources when the window is closed), and a window listener is added in order to exit the application as soon as the frame is closed.

Running the Java® interpreter (using _java_ _SwingApplication1)_ will execute the program and give the following window:

{{< resource "78991a57-f994-7e6e-1fa6-17b608d9c421" >}}

Often, the source code file can be written in a way that it can be used both as an applet and an application. The above example is rewritten in way to facilitate such a use. The source code is provided below:

> AppletApplication1.java
> 
> _import java.awt.\*;_  
> _import javax.swing.\*;_  
> _import java.awt.event.\*;_
> 
> _public class AppletApplication1 extends JApplet_  
> _{_
> 
>  _public void init()_  
>  _{_  
>  _Icon icon = new ImageIcon("1.124.gif", "1.124 GIF");_  
>  _JLabel label = new JLabel(" Test", icon, SwingConstants.CENTER);_  
>  _getContentPane().add(label);_  
>  _}_  
>  
> 
>  _public static void main(String args\[\])_  
>  _{_  
>  _final JFrame myFrame = new SwingApplication1();_  
>  _JApplet myApplet = new AppletApplication1();_  
>  _myApplet.init();_
> 
>  _myFrame.setContentPane(myApplet.getContentPane());_  
>  _myFrame.setBounds(100,50,500,150);_  
>  _myFrame.setVisible(true);_
> 
>  _myFrame.setDefaultCloseOperation(WindowConstants.DISPOSE\_ON\_CLOSE);_
> 
>  _myFrame.addWindowListener(new WindowAdapter()_  
>  _& #160;          {_  
>  _& #160;             public void windowClosed(WindowEvent e)_  
>  _& #160;                  {_  
>  _& #160;                     ; System.exit(0);_  
>  _& #160;                  }_  
>  _& #160;          }                    );_  
>  _}_
> 
> _}_

Mixing AWT and Swing
--------------------

Attention should be given when [mixing AWT and Swing](http://java.sun.com/products/jfc/tsc/swingdoc-archive/mixing.html) components, since when lightweight components overlap with heavyweight components, the heavyweight components are always painted on top. In general, it should [mixing AWT and Swing](http://java.sun.com/products/jfc/tsc/swingdoc-archive/mixing.html) components should not be mixed whenever possible. The "depth" at which components are displayed in a container is represented by the Z-order. The latter is determined by the order with which each component is added to the container, i.e. the first component to be added to a container has the highest Z-order which means that it is displayed in front of all other components added to that container. When lightweight and heavyweight components are mixed, the lightweight components, which need to reside in a heavyweight container, have the same Z-order of their container, and within it the order of each of the lightweight components is determined by the order in which they are added to the container. Note, that whenever a container is extended and the _paint()_ method is overridden, the superclass _paint()_ method should be explicitly invoked using _super.paint()_ to force drawing of the lightweight components.

When _Swing_ popup menus, which are lightweight, are mixed with a heavyweight component, the latter overlaps the former. This can be avoided by forcing the popup menus to be heavyweight using the method _setLightWeightPopupEnabled_() of the _JPopupMenu_ class. A similar problem happens with a _JScrollPane_ instance when any heavyweight components to it. Because there is no option of setting the _JScrollPane_ as a heavyweight, the _AWT_ ScrollPane can be used instead, which works fine with both lightweight and heavyweight components. Finally, heavyweight components should be avoided (i.e. not be added) to _Swing_ internal frames, i.e. to a _JInternalFrame_ instance.

Layout Managers
---------------

Layout managers (such as the _BorderLayout__, _ _BoxLayout__,_ _GridLayout__, _ _FlowLayout__, _ _CardLayout__, _ _GridBagLayout_) are used to determine the size and position of the components that are contained in a container. Each container is provided a default layout manager, which, however, can be changed using the _setLayout_() method and as an argument a newly created instance of the preferred layout manager. The minimum, preferred, and maximum sizes of a component can also be specified to the layout manager, as well as the preferred alignment.

Painting System
---------------

The _AWT_ painting system controls the painting of a Swing GUI, starting with the highest component that needs to be repainted and going down the hierarchy of containers, using the event-dispatching thread. The painting of swing components occurs whenever necessary. Swing uses double buffering to improve the efficiency and quality of the provided GUI. During painting, each component paints itself before any of the components that it contains. A Swing top-level container is painted on-screen using one of the methods: _setVisible(true)_, _show()_, or _pack()_. Painting starts with the highest component that needs to be repainted and moving down the containment hierarchy, i.e. each component paints itself before any of the components it contains.

Swing performs, by default, double-buffered to ensure smoothness and avoid flushing. Double buffering is essentially implemented by an offscreen buffer in which all painting takes place, and then it is flushed to the screen.

Event Handling
--------------

The event handling features of the Swing (and AWT) components allow to a Java® program to respond to external events, such as the interaction of the user with the GUI. Events are handled by event handlers that are registered with event sources. Any _Swing_ component can be notified for the occurrence of any event simply by implement the corresponding interface and registering it as an event listener on a relevant event source. The latter is usually component, e.g. a button. for each event there is a corresponding object which provides all the relevant information. An event handler is implemented by:

*   either
    *   implementing the corresponding listener interface, or
    *   extending a class that implements that interface
*   implement the method in the listener (interface or subclass)
*   adding that kind of listener to a component

Sometimes, anonymous inner classes are used to keep the code clearer and the event handler closer to the point where it is registered. The event-handling code executes in the event-dispatching thread (single thread) ensuring that each event handler will execute in sequence allowing a previous event handler finish executing before the next one starts execution. Therefore, the code in the event handlers should be either very short and quick to execute, or another thread should be initiated to execute the code, in order to not harm the performance of the program. Otherwise, painting, which also executes on the event-dispatching thread, will not occur while an event is being handled.

Threads
-------

_Swing_, in general, is not thread safe, because a _Swing_ component can be accessed by only one thread at a time, which, in general, is the _event-dispatching thread_. Because Swing is not thread safe, Swing components, in general, should be accessed only from the event-dispatching thread. The _event-dispatching thread_ is the thread that invokes callback methods (e.g. _paint()_ and _update()_ functions) and event handler methods. Swing has been designed to be not thread safe in order to avoid the overhead of multithreading (e.g. obtaining and releasing locks) and to simplify the subclassing of its component. It is not allowed to access Swing components from any thread other than the event-dispatching thread.

However, some _Swing_ components support multithread access. Actually after the realization of a _Swing_ component code that might affect or depend on the state of that component should be executed in the event-dispatching thread. Realization of a component means after the component is available for painting on screen, after it is painted or become ready to be painted using one of the methods: _setVisible(true)_, _show()_, or _pack()._

The access only through the _event-dispatching thread_ is not required in the following cases:

*   when dealing with thread safe methods (as specified in the _Swing_ API documentation) to construct and show a GUI in the main thread of  an application, as long as  no components have been realized in the current runtime environment
*   constructing and manipulating the GUI in an applet's _init()_ method, as long as the components have not been made visible, i.e. the method _show()_ or _setVisible(true)_ has never been called on the actual applet object
*   methods _repaint()_ and _revalidate()_ are safe to call from any thread

In general, Swing it is not safe to access Swing components from any thread other than the event-dispatching thread. However, there are times that it is preferable to update Swing components from another thread, or perform time-consuming operations on a separate thread, and not use the _event-dispatching thread_. In those cases, _Swing_ provides the methods _invokeLater_() and _invokeAndWait_() in the _SwingUtilities_ class, which can be used to queue a runnable object on the event dispatch thread. They essentially allow a block of code from another thread to be invoked and executed by the event-dispatching thread. Both methods can be used to access Swing components from a thread other than the event-dispatching thread. Method _invokeLater()_ queues the runnable object and returns immediately, while _invok eAndWait()_ waits until the runnable object's _run()_ method has started before returning. Only the _invokeLater_() (and not _invokeAndWait_()) method can be called from the event dispatching thread.