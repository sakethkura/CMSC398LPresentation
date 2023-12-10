# CMSC398LPresentation

I will be talking about the Task Scheduler problem. I found this problem cool because it involves handling cases with priority and processing a list of tasks in the most optimal way. Here is the problem statement.

Given a characters array tasks, representing the tasks a CPU needs to do, where each letter represents a different task. Tasks could be done in any order. Each task is done in one unit of time. For each unit of time, the CPU could complete either one task or just be idle.

However, there is a non-negative integer n that represents the cooldown period between two same tasks (the same letter in the array), that is that there must be at least n units of time between any two same tasks.

Return the least number of units of times that the CPU will take to finish all the given tasks.

Example 1:

Input: tasks = ["A","A","A","B","B","B"], n = 2
Output: 8
Explanation: 
A -> B -> idle -> A -> B -> idle -> A -> B
There is at least 2 units of time between any two same tasks.
Example 2:

Input: tasks = ["A","A","A","B","B","B"], n = 0
Output: 6
Explanation: On this case any permutation of size 6 would work since n = 0.
["A","A","A","B","B","B"]
["A","B","A","B","A","B"]
["B","B","B","A","A","A"]
...
And so on.
Example 3:

Input: tasks = ["A","A","A","A","A","A","B","C","D","E","F","G"], n = 2
Output: 16
Explanation: 
One possible solution is
A -> B -> C -> A -> D -> E -> A -> F -> G -> A -> idle -> idle -> A -> idle -> idle -> A
 

Constraints:

1 <= task.length <= 104
tasks[i] is upper-case English letter.
The integer n is in the range [0, 100].


Some things to consider are that once we finish a task (or letter), we must reach the cool down timer in order to start the same task again. Another thing is that if there is no cool down timer, then the total amount of time will be the total number of tasks.

My initial approach was to use to store the tasks in terms of their frequency and then use a max heap to sort them from largest to smallest. Then, when I process the highest priority task, I would decrease the count and add it back to the max heap if it still exists. But, I was struggling where to go from there.

Here is the actual solution.





