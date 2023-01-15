

/**
 * Doubly Linked List Queue Class
 *
 * @param <T> generic container
 */

/**
 * Initialize the instance variables of this queue
 * @param <T> generic container
 */
public class DLLQueue<T> {

    private DoublyLinkedList<T> queue;

    /**
     * Constructor for Doubly Linked List Queue
     */

    public DLLQueue() {
        queue = new DoublyLinkedList<>();
    }

    /**
     * Returns the number of elements currently stored in this queue
     * @return Returns the number of elements currently stored in this queue
     */

    public int size() {
        return queue.size();
    }

    /**
     * Returns true if this queue is empty, false otherwise
     * @return Returns true if this queue is empty, false otherwise
     */

    public boolean isEmpty() {
        return queue.isEmpty();
    }

    /**
     * Adds the given data to this queue
     * @param data data of type T
     * @throws IllegalArgumentException if data is null
     */

    public void enqueue(T data) {
        if (data == null) { //checks if data is null
            throw new IllegalArgumentException();
            //throws IllegalArgumentException if data is null
        }
        queue.add(data); //adds the given data to the queue
    }

    /**
     * Removes and returns the top/first element from this queue
     * @return Returns null if this queue has no elements.
     * Else, return the top/first element
     */

    public T dequeue() {
        if (isEmpty()) { // checks is the queue size is zero
            return null; // returns null is the queue size is zero
        } else {
            return queue.remove(0); // removes and returns the top element of the queue
        }

    }

    /**
     * Peeks and returns the top element from this queue
     * @return Returns null if this queue has no elements.
     * Else, returns the top element from this queue
     */

    public T peek() {
        if (isEmpty()) { //checks if queue size is zero
            return null; //returns null if queue size is zero
        } else {
            return queue.get(0); //peeks and returns the top element from the queue
        }
    }

}
