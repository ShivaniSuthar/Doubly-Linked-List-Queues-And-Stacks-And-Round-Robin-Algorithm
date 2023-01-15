

/**
 * Doubly Linked List Stack Class
 *
 * @param <T> generic container
 */

/**
 * Initialize the instance variables of this stack
 * @param <T> generic container
 */
public class DLLStack<T> {

    private DoublyLinkedList<T> stack;

    /**
     * Constructor for Doubly Linked List Stack
     */

    public DLLStack() {
        stack = new DoublyLinkedList<>();
    }

    /**
     * Returns the number of elements currently stored in this stack
     * @return Returns the number of elements currently stored in this stack
     */

    public int size() {
        return stack.size();
    }

    /**
     * Returns true if this stack is empty, false otherwise
     * @return Returns true if this stack is empty, false otherwise
     */

    public boolean isEmpty() {
        return stack.isEmpty();
    }

    /**
     * Add the given data to this stack
     * @param data data of type T
     * @throws IllegalArgumentException if data is null
     */

    public void push(T data) {
        if (data == null) { //checks if data is null
            throw new IllegalArgumentException();
            //throws IllegalArgumentException if data is null
        }
        stack.add(data); //Adds the given data to the stack

    }

    /**
     * Removes and returns the top/first element from this stack
     * @return Returns null if this stack has no elements.
     * Else, returns the top/first element
     */

    public T pop() {
        if (isEmpty()) { //checks if the stack size is zero
            return null;
        } else {
            // removes and returns the top element of the stack
            return stack.remove(stack.size() - 1);
        }


    }

    /**
     * Peeks and returns the top element from this stack
     * @return Return null if this stack/queue has no elements.
     * Else, returns the top element from this stack
     */

    public T peek() {
        if (isEmpty()) { //checks if stack size is zero
            return null;
        } else {
            return stack.get(stack.size() - 1);
            //peeks and returns the top element of the stack
        }
    }

}
