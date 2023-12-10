# CMSC398LPresentation

I will be talking about the Task Scheduler problem. I found this problem cool because it involves handling cases with priority and processing a list of tasks in the most optimal way. Here is the problem statement.


<img width="696" alt="Screen Shot 2023-12-10 at 5 26 59 PM" src="https://github.com/sakethkura/CMSC398LPresentation/assets/49348685/09034027-04a5-4426-96c3-7889d947997d">


Some things to consider are that once we finish a task (or letter), we must reach the cool-down timer to start the same task again. Another thing is that if there is no cool-down timer, then the total amount of time will be the total number of tasks.

My initial approach was to store the tasks in terms of their frequency and then use a max heap to sort them from largest to smallest. Then, when I process the highest priority task, I would decrease the count and add it back to the max heap if it still exists. But, I was struggling with where to go from there.

Here is the actual solution.

<img width="498" alt="Screen Shot 2023-12-10 at 5 25 17 PM" src="https://github.com/sakethkura/CMSC398LPresentation/assets/49348685/b058e642-b8f4-4c71-a2b0-7fe563d6efa9">

To start with, if there is no cool time, then the total time will be the number of tasks to process. Here, we create a max heap based on the frequency of the tasks as previously mentioned. We then use a queue as a waiting area for tasks that have been processed and are in the cool-down time. We also create a time variable to keep track of the total elapsed time. Essentially, when we process a task and its frequency is > 1, then we add it to the queue with the time it is done cooling down. If the queue still exists and the top element's time has been reached, then we pop it off the queue and add it back to the max heap to be processed. Once the max heap and queue have no more elements, then we can return the time since all of the tasks have been processed. 

Time Complexity

In the worst case, we may have a situation where we get the same task many times, and so we would need to wait after every single task. Within the code, there are only traversals across the tasks in the worst case to make and process the max heap. So, the time complexity will be O(len(tasks) * n), where n = cool-down time

Space Complexity

In the code, we are creating the max heap and queue. In the worst case, the max heap would store len(tasks) elements and the same with the queue. Since, O(len(tasks)) + O(len(tasks)) = O(len(tasks)), the space complexity would be O(len(tasks)).












