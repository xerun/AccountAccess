# AccountAccess
Synchronization mechanisms to access 10 account multiple times and keep the balance same

Task 1

The requirement is not met due to race condition. The bug is caused when multiple threads try to access a shared recourse at the same time. It can be fixed by restricting resource access to one thread at a time by using the synchronized keyword.

Task 2

The starting order of the threads is determined by the Java Virtual Machine (JVM). 
Consistency of the account will not be preserved by changing the starting order because the thread will be running parallelly regardless the starting order.

Task 3

The critical section of the code is balance variable, multiple threads are trying to access the balance variable to read or write at the same time, as a result the final output becomes incorrect.
balance = balance + amount; // deposit balance
balance = balance - amount; // withdraw balance

Task 4

Method level synchronization is used in the Withdraw and Deposit functions keep the balance consistency

Task 5

Block level synchronization is used in the Withdraw and Deposit functions critial section where the balance variable is shared with both Withdraw and Deposit function

Task 6

One significant difference between synchronized method and block is that, synchronized block generally reduce scope of lock. As scope of lock is inversely proportional to performance, it’s always better to lock only critical section of code. By using synchronized block we can lock critical section of code instead of locking whole deposit() or withdraw() methods. This improves performance drastically because locking is only required one or two times.
