

/**
 * Round Robin Class
 *
 */
public class RoundRobin {

    /* constants */
    private static final String TASK_HANDLED = "All tasks are already handled.";

    /* instance variables */
    private DoublyLinkedList<Task> waitlist, finished;
    private int quantum, burstTime, waitTime;

    /**
     * Constructor that calls the constructor below with a default quantum of 4
     *
     * @param toHandle Tasks to handle
     */

    public RoundRobin(Task[] toHandle) {

        this(4, toHandle);

    }

    /**
     * Constructor that initializes the instance variables
     *
     * @param quantum  An integer that stores quantum time unit
     * @param toHandle Tasks to handle
     * @throws IllegalArgumentException if quantum is less than 1
     * @throws IllegalArgumentException if toHandle is null or if
     * no tasks have been passed in
     */

    public RoundRobin(int quantum, Task[] toHandle) {

        if (quantum < 1) {
            throw new IllegalArgumentException();
            // throws exception if quantum is less than 1
        }

        if (toHandle == null || toHandle.length == 0) {
            throw new IllegalArgumentException();
            // throws exception if condition above is not met
        }
        //assigning bustTime, watTime, and finished
        burstTime = 0;
        waitTime = 0;
        this.quantum = quantum;
        waitlist = new DoublyLinkedList<Task>();
        finished = new DoublyLinkedList<Task>();
        for (int i = 0; i < toHandle.length; i++) {
            waitlist.add(toHandle[i]);
        }
    }

    /**
     * This goes through the tasks in the waitlist,
     * schedules them in order for one quantum period,
     * and then returns it to the queue or marks it completed as necessary.
     * It keeps track of the burst and wait times.
     * It loops through the waitlist until no more
     * tasks need to be scheduled. It finally returns a String
     *
     * @return Returns of one two strings: "TASK_HANDLED" or "All tasks are handled..."
     */

    public String handleAllTasks() {
        if (waitlist.isEmpty()) {
            return TASK_HANDLED;
            //if waitlist is empty, return TASK_HANDLED
        }

        //while loop for incrementing burst and wait times
        while (true) {

            Task t = waitlist.get(0);
            waitlist.remove(0);
            for (int j = 0; j < quantum; j++) {
                if (t.handleTask()) {
                    burstTime = burstTime + 1;
                    waitTime = waitTime + waitlist.size();

                } else {
                    break;
                }
            }
            //if and else statements for adding to waitlist and finished
            if (!t.isFinished()) {
                waitlist.add(t);
            } else {
                finished.add(t);
            }
            // final string implementation
            if (waitlist.isEmpty()) {
                String s = "All tasks are handled within " + burstTime
                        + " units of burst time and " + waitTime + " units of wait time."
                        + " The tasks are finished in this order:\n";
                for (int k = 0; k < finished.size() - 1; k++) {
                    s = s + finished.get(k) + " -> ";
                }
                s = s + finished.get(finished.size() - 1);
                return s;
            }
        }

    }

    /**
     * Main method for testing.
     *
     * @param args command-line arguments
     */
    public static void main(String[] args) {
        Task[] test1 = {new Task("A", 3), new Task("B", 4),
                new Task("C", 4), new Task("D", 12),
                new Task("E", 6), new Task("F", 3)};
        RoundRobin rr1 = new RoundRobin(3, test1);     // Quantum: 3, ToHandle: test1
        System.out.println(rr1.handleAllTasks());   // Burst: 32, Wait: 86, Order: AFBCED
        System.out.println();
        System.out.println(rr1.handleAllTasks());   // TASK_HANDLED
        System.out.println();

        Task[] test2 = {new Task("A", 9), new Task("B", 8),
                new Task("C", 6), new Task("D", 4),
                new Task("E", 4), new Task("F", 3)};
        RoundRobin rr2 = new RoundRobin(test2);  // Quantum: 4, ToHandle: test2
        System.out.println(rr2.handleAllTasks());   // Burst: 34, Wait: 123, Order: DEFBCA
        System.out.println();
        System.out.println(rr2.handleAllTasks());   // TASK_HANDLED
        System.out.println();

        Task[] test3 = {new Task("A", 7), new Task("B", 5),
                new Task("C", 3), new Task("D", 1),
                new Task("E", 2), new Task("F", 4),
                new Task("G", 6), new Task("H", 8)};
        RoundRobin rr3 = new RoundRobin(3, test3);     // Quantum: 3, ToHandle: test3
        System.out.println(rr3.handleAllTasks());   // Burst: 36, Wait: 148, Order: CDEBFGAH
        System.out.println();
        System.out.println(rr3.handleAllTasks());   // TASK_HANDLED
        System.out.println();
    }
}
