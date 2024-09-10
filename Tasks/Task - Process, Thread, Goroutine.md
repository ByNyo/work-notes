### **Process**
The Instance of a computer program that is being executed by one or many threads.
### **Thread**
A single sequential flow of control within a program.
### **Goroutine**
A function or method that executes independently and simultaneously in connection with any other Goroutines in your program.
**Example:**

```go
// Goroutine (replace <yourfunction> with your funciton)
go yourfunction()

// Goroutine that repeats forever
go func() {
	for {
		fmt.Println("Every 500ms")
		time.Sleep(time.Milisecond * 500)
	}
}
```
### **Questions**
**What is the difference between processes, threads and goroutines?**

| Process                          | Thread                                             | Goroutine                                    |
| -------------------------------- | -------------------------------------------------- | -------------------------------------------- |
| Processes are the whole program. | A thread is a sequence of programmed instructions. | A goroutine is just a function of a program. |
**What are performance implications of each?**

|      | Process                                                                                                                                                                                            | Thread                                                                                                | Goroutine                                                                        |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| Good | If one process crashes it doesn't affect others because they are isolated, by having their own memory space.                                                                                       | Applications can run multiple operations in parralel on different cores.                              |                                                                                  |
| Bad  | The overhead associated with context switching between processes is the strongest negative impact, as it can significantly reduce performance, especially when processes are frequently switching. | Multiple threads can compete for access to shared resources which can lead to contention and blocking | goroutines are running in the background so they shouldn't decrease performance. |
**What is PID? Why is it important? Why might it be obsolete?**
**PID** (Process Identifier) is a unique numercial identifier assigned by the operating system to each process running on a system. Each **PID** (Process Identifier) is unique within the operating system. It is important to keep the processes seperated. It might be obsolete, because more advanced and flexible identification methods can be used.
### **Task**
List all the processes in terminal: ps
Print processes tree: ps aux
Run Weather Forecast Application in Background: start the programm and press STRG + Z
Pipe "ps" command output to grep and find PID of go app: ps | grep go
"ps" command help: man ps
