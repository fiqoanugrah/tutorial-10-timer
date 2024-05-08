## **Hi! :wave:, I'm Muhammad Fiqo Anugrah and this is my repo for Tutorial 10 Adpro C**


> REFLECTION

>> 1.2. Understanding how it works.

Adding such a "Hey hey sentence right after the spawner.sparwn (...);
and look at what happened. This is a result capture of the execution.

<img width="400" alt="Screenshot 2024-05-08 at 17 09 48" src="https://github.com/fiqoanugrah/tutorial-10-timer/assets/87713462/b9127acb-e89e-485e-88d9-0ccd416242b7">
<img width="525" alt="Screenshot 2024-05-08 at 17 10 09" src="https://github.com/fiqoanugrah/tutorial-10-timer/assets/87713462/49df7a5f-5fe6-4e6a-9b51-49b16d23955c">

>> Code Explanation
Executor and Spawner Setup: The code begins by creating an executor and a spawner using the new_executor_and_spawner() function. The exact implementation of this function isn't shown but it likely sets up the infrastructure for running asynchronous tasks.
Asynchronous Task: A task is spawned which first prints "Fiqo's Computer: howdy!", then it pauses for two seconds (using a timer future that completes after this duration), and finally prints "Fiqo's Computer: done!".
Main Thread Print: While the asynchronous task waits to complete, the main function immediately proceeds to print "Fiqo's Computer: hey hey!".
Dropping the Spawner: The spawner is dropped so no more tasks can be added to the executor.
Executor Runs to Completion: The executor is then run, which will process the remaining tasks in the queue (i.e., finishing the spawned task).

>> Program Output Explanation
The output in the terminal, is:
Fiqo's Computer: hey hey!
Fiqo's Computer: howdy!
Fiqo's Computer: done!

>> This sequence confirms that:
The "hey hey!" message is printed immediately from the main thread.
The asynchronous task starts and prints "howdy!".
After a two-second delay, the task completes and prints "done!".

This shows the non-blocking nature of asynchronous tasks. While the async task is waiting to complete its delay, the main program continues execution and prints "hey hey!". After the delay, the task resumes and completes its execution.

## Conclusion

This example illustrates the power of asynchronous programming in Rust, allowing multiple tasks to proceed without blocking each other, thereby increasing the efficiency of the program.



