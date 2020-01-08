 ### What is concurrency? What is parallelism? What's the difference?
 Concurrency is the concept of where you have multiple tasks running though not at the same time. This can for example be implemented on a singel core cpu.
 While parallelism is the concept where you execute tasks in parallel at the same time which concurrency does not. There is a massive preformance advantage to concurrency here since you don´t need to wait for other tasks to finish first. However ofc care needs to be taken to paralell tasks which are dependent on each other.
 
 ### Why have machines become increasingly multicore in the past decade?
 Since we have moved to using computers and systems which are able and requred to run multiple tasks at the same time. Multicores can then be used to execute indepedent tasks in parallel so we do not lose preformance. 
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 Problems where you have system resources which can only be accessed by one task at the time. Concurrency allows us to scheduale and maybe prioritize if its implemented which tasks need to run first.
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 Both, its easier to make multitask programs where you do not want a sequancial execution. Though it requires the programmer to deal with larger complexity, maybe a type of OS to handle the tasks. 
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 * Processes: Is the program being executed 
 * Threads: Seperate sequences managed by a scheduer which is normally controlled by the OS
 * Green Threads: "Virtual" threads created by non-os routines/libs which is controlled by the program which spawned it and not handeled by the os itself
 * CoRoutines: Execution which is purly concurrent are executed on for example the same thread and are not able to run in paralell compeared to threads.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 * pthread_create(): creates a system thread
 * threading.Thread(): creates coroutines as a "thread" which are executed in non-paralell
 * go: green thread
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 It is a type of mutex where only one thread can hold controll of the python interperter at the time.
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 We can use multiprocessing module to actually make separete paralell processes.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 Limites the number os operating system threads the go process can see and use.
