**EXERCISE CHAPTER 4**

**1.	Provide three programming examples in which multithreading provides better performance than a single-threaded solution**
   
    a.	Image processing
        Single-thread : The process is done sequentially, pixel by pixel for an image of 4000x3000 = 12 million pixels, it takes a long time.
        Multi-thread : Each thread processes a subset of images in parallel. Significantly reduces processing time, especially on multi-core processors.
  	
    b.	Web Server Handling
        Single-thread : Requests are processed one by one Client must wait for the previous request to complete. Requests are handled one by one, so it is slow if there are many connections.
        Multi-thread : Each client request is processed by a separate thread. This allows the server to handle multiple requests simultaneously. Faster response and better scalability.
  	
    c.	Matrix Multiplication
        Single-thread : O(n³) complexity executed serially long execution time
        Multi-thread : Division of matrix rows to different threads,On 8-core CPUs, speedup ~7-8x.Used in libraries such as NumPy, TensorFlow

**2.	Using Amdahl's Law, calculate the speedup gain of an application that has a 60 percent parallel component for (a) two processing cores and (b) four processing cores.**

      Amdahl's Law is used to calculate the maximum acceleration that can be achieved when a portion of the program is run in parallel.
       
       Amdahl's Law:
       Speedup = 1/(1−p)+p/n = (1−p)+np1
       p = bagian paralel (0.6)
       n = jumlah core
       
       Hasil:
       2 Core: Speedup = 1 / (0.4 + 0.3) = 1 / 0.7 ≈ 1.43
       4 Core: Speedup = 1 / (0.4 + 0.15) = 1 / 0.55 ≈ 1.82
       So in processing using two processing cores can be 1.43 times faster than being done serially and using four processing cores is 1.82 times faster than being done serially.

**3.	Does the multithreaded web server described in Section 4.1 exhibit task parallelism or data parallelism?**
   
       Multithreaded web servers as described in Section 4.1 generally adopt task parallelism because each thread handles different and independent tasks (requests) from different clients, such as reading HTML           files, querying databases, or processing file uploads, where each request has its own operations and data that are not shared between threads.

**4.	What are the two differences between user-level threads and kernel-level threads? Under what conditions is one type superior to the other?**

       a. Management thread 
           User : Managed entirely by applications or libraries in user space, without involving the operating system. This management includes thread creation, scheduling, and termination. The operating system                     does not know about the existence of user-level threads, so it cannot directly schedule or control them.
           Kernel : Managed entirely by the operating system, with the kernel handling thread creation, scheduling, and termination. Each kernel-level thread is viewed as a separate entity by the kernel and                           scheduled independently.
       
       b. CPU Population and Scheduling
           User : Since these threads are only managed by the application, the operating system does not know how many threads are running in the application. Therefore, the application must handle its own                          internal scheduling.
           Kernel : Each thread is treated as a separate entity by the kernel, allowing the operating system to schedule threads independently and more efficiently utilize the CPU.
     	
       c. Superior User-Level Threads if
              1.	When the overhead of scheduling and managing threads should be minimized
              2.	Application portability is a priority.
              3.	Large number of threads.
              d.	read Superior Kernel Level
              1.	When applications require complex I/O handling or parallelism
              2.	Applications often perform blocking operations. 
              3.	The kernel itself must be multithreaded.

**5.	Describe the actions taken by the kernel to perform context-switches between kernel-level threads.**

          Actions taken by the kernel in the process of context switching between kernel-level threads:
          
          1.Saving the Context of the Current Thread
          2.Determining the Next Thread
          3.Loading the Context of the New Thread
          4.Switching Control to the New Thread
