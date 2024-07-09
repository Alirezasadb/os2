# os2
Program Overview

This Java program simulates a real-time task scheduling system with multiple processors. It supports two scheduling algorithms: Rate Monotonic (RM) and Earliest Deadline First (EDF). Tasks are assigned to processors with specific resource requirements, periods, and execution times. The program manages the execution of these tasks while ensuring the availability of required resources.

Key Components

1. Resources
The program uses three types of resources:
- R1
- R2
- R3

These resources have initial quantities that can be modified as needed.

2. Processors
The system supports multiple processors. Each processor has:
- A ready queue for tasks that are ready to run.
- A running task that is currently being executed.
- A CPU utilization metric to track how much of the processor's capacity is being used.
- A mutex to handle synchronization.

3. Tasks
Tasks have the following attributes:
- id: Unique identifier for the task.
- period: Time period of the task.
- executionTime: Time required to execute the task.
- r1, r2, r3: Resource requirements for the task.
- processor: Processor to which the task is assigned.
- repetitions: Number of times the task needs to be executed.
- deadline: Deadline for task completion.
- remainingRepetitions: Number of remaining executions.
- running: Flag indicating if the task is currently running.
- completed: Flag indicating if the task is completed.

4. Scheduling Algorithms
The program supports two scheduling algorithms:
- **Rate Monotonic (RM)**: Prioritizes tasks with shorter periods.
- **Earliest Deadline First (EDF)**: Prioritizes tasks with earlier deadlines.

Program Execution

Initialization
1. Resources are initialized with their respective quantities.
2. Processors are created and initialized.
3. Tasks are defined with specific attributes and assigned to processors.
4. Deadlines for tasks are calculated based on their periods and repetitions.

Main Thread
The main thread handles:
- Starting processor threads.
- Printing the state of the system every second, including resource availability, waiting queue, and the status of each processor's ready queue and running task.

Processor Threads
Each processor thread handles:
- Checking if there are any running tasks.
- Scheduling tasks from the ready queue or the waiting queue based on the selected algorithm.
- Managing resource acquisition and release for tasks.
- Executing tasks and updating their status and remaining execution time.
- Handling task completion and missed deadlines.

Usage

Running the Program
To run the program, compile and execute the `Main` class. The program will initialize resources, processors, and tasks, and then start the main thread to manage task scheduling and execution.

Customizing the Program
- **Resources:** Modify the initial quantities of R1, R2, and R3 in the `main` method.
- **Tasks:** Add or remove tasks in the `main` method. Specify task attributes such as period, execution time, resource requirements, assigned processor, and repetitions.
- **Scheduling Algorithm:** Change the value of the `algorithm` variable to either `"Rate Monotonic"` or `"EDF"` to switch between scheduling algorithms.

Output
The program prints the state of the system every second, including:
- Available resources.
- Waiting queue status.
- Status of each processor, including CPU utilization, ready queue, and running task.

Example
Here is an example output for the program:

----- Time Unit: 1 -----
Available Resources: R1=4 R2=2 R3=2
Waiting Queue: Empty
Processor 1
 CPU Utilization: 0.0
 Ready Queue: T1 T2 
 Running Task: Empty
Processor 2
 CPU Utilization: 0.0
 Ready Queue: T3 
 Running Task: Empty
Processor 3
 CPU Utilization: 0.0
 Ready Queue: Empty
 Running Task: Empty


This output indicates that at time unit 1:
- All resources are available.
- The waiting queue is empty.
- Processor 1 has tasks T1 and T2 in its ready queue but is not running any task.
- Processor 2 has task T3 in its ready queue but is not running any task.
- Processor 3 has no tasks in its ready queue and is not running any task.

Conclusion
This program provides a basic simulation of a real-time task scheduling system with support for multiple processors and different scheduling algorithms. It can be customized to fit specific requirements by modifying resource quantities, task attributes, and scheduling algorithms.
