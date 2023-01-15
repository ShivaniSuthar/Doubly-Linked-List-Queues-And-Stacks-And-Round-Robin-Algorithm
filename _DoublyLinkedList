

import java.util.AbstractList;

/**
 * Doubly Linked List Class
 *
 */
public class DoublyLinkedList<T> extends AbstractList<T> {

    /* DLL instance variables */
    private int nelems;
    private Node head;
    private Node tail;

    /**
     * Node for chaining together to create a linked list
     *
     */
    protected class Node {

        /* Node instance variables */
        T data;
        Node next;
        Node prev;

        /**
         * Constructor to create singleton Node
         *
         * @param element of type T
         */
        private Node(T element) {
            this.data = element;
        }

        /**
         * Constructor to create singleton link it between previous and next
         *
         * @param element  Element to add, can be null
         * @param nextNode successor Node, can be null
         * @param prevNode predecessor Node, can be null
         */
        private Node(T element, Node nextNode, Node prevNode) {
            this.data = element;
            this.prev = prevNode;
            this.next = nextNode;
        }

        /**
         * Set the element
         *
         * @param element new element
         */
        public void setElement(T element) {
            this.data = element;
        }

        /**
         * Accessor to get the Nodes Element
         *
         * @return returns data
         */
        public T getElement() {
            return data;
        }

        /**
         * Set the next node in the list
         *
         * @param n new next node
         */
        public void setNext(Node n) {
            this.next = n;
        }

        /**
         * Get the next node in the list
         *
         * @return the successor node
         */
        public Node getNext() {
            return next;
        }

        /**
         * Set the previous node in the list
         *
         * @param p new previous node
         */
        public void setPrev(Node p) {
            this.prev = p;
        }


        /**
         * Accessor to get the prev Node in the list
         *
         * @return predecessor node
         */
        public Node getPrev() {
            return prev;
        }

        /**
         * Remove this node from the list.
         * Update previous and next nodes
         */
        public void remove() {
            prev.setNext(next);
            next.setPrev(prev);
        }
    }

    /**
     * Creates a new, empty doubly-linked list.
     */
    public DoublyLinkedList() {
        this.nelems = 0;
        this.head = new Node(null);
        this.tail = new Node(null, null, head);
        head.setNext(tail);
    }

    /**
     * Add an element to the end of the list
     *
     * @param element data to be added
     * @return whether or not the element was added
     * @throws NullPointerException if data received is null
     */
    @Override
    public boolean add(T element) throws NullPointerException {
        // Throw exception if element is null
        if (element == null) {
            throw new NullPointerException();
        }

        // Implementation
        Node n = tail.getPrev();
        Node m = new Node(element, tail, n);
        n.setNext(m);
        tail.setPrev(m);
        nelems++;
        return true;
    }



    /**
     * Adds an element to a certain index in the list, shifting exist elements
     * create room. Does not accept null values.
     *
     * @param index   An integer that specifies the index of where to insert a node
     * @param element Parameter of type T that specifies the element
     * @throws IndexOutOfBoundsException Exception thrown if index
     * is less than 0 or greater than size
     * @throws NullPointerException Exception thrown if received data is null
     */
    @Override
    public void add(int index, T element)
            throws IndexOutOfBoundsException, NullPointerException {

        //if the index is out of bounds, it throws the exception
        if (index > nelems || index < 0) {
            throw new IndexOutOfBoundsException();
        }

        //if element is null, it throws the exception
        if (element == null) {
            throw new NullPointerException();
        }

        //if the index is 0...
        if (index == 0) {
            Node j = head.getNext();
            Node m = new Node(element, j, head); //makes a node
            head.setNext(m); //assigns m.next to head
            j.setPrev(m); //assigns head to m
            nelems = nelems + 1; //increments nelems
        } else if (index == nelems) { //else, if the index equals nelems...
            add(element);
        } else { // otherwise...
            Node n = head.getNext();
            // Iterate up to index
            for (int i = 0; i < index; i++) {
                n = n.getNext();
            }
            Node k = n.prev;
            Node m = new Node(element, n, k);
            k.setNext(m);
            n.setPrev(m);
            nelems = nelems + 1; //increments nelems
        }
    }

    /**
     * Clear the linked list
     */
    @Override
    public void clear() {
        // While list is not empty
        while (!isEmpty()) {
            remove(0);
        }
    }

    /**
     * Determines if the list contains the data element anywhere in the list.
     *
     * @param element Parameter of type object that specifies the element
     * @return Returns a boolean. Returns true if the list contains
     * the specified element at least once
     * @throws NullPointerException Exception thrown if element is null
     */
    @Override
    public boolean contains(Object element) {
        T data = (T) element; //assigns data to element
        if (element == null) {
            throw new NullPointerException(); //throws exception if element is null
        }

        Node n;

        n = head.getNext();
        while (n != tail) {
            if (n.getElement().equals(data)) { //if the element is equal to the data...
                return true; //returns true
            }
            n = n.getNext();

        }
        return false; //else, returns false
    }

    /**
     * Retrieves the element stored with a given index on the list.
     *
     * @param index An integer that specifies the index at which
     * the data should be accessed
     * @return returns the data contained in the node at the specified index (type T)
     * @throws IndexOutOfBoundsException Exception thrown if
     * index is outside the range [0, size - 1]
     */
    @Override
    public T get(int index) throws IndexOutOfBoundsException {
        //throws exception if index is out of bounds
        if (index < 0 || index >= nelems) {
            throw new IndexOutOfBoundsException();
        }

        return getNth(index).getElement();
    }

    /**
     * Helper method to get the Nth node in our list
     *
     * @param index An integer that specifies the index to access the node
     * @return the node in the specified index of the list (type Node)
     */
    private Node getNth(int index) {
        Node n = head.getNext(); //assigns node n to head
        //assigns n to n.next while int i is less than index
        for (int i = 0; i < index; i++) {
            n = n.getNext();

        }
        return n;

    }

    /**
     * Determine if the list empty
     *
     * @return returns a boolean. Return true if the list
     * contains no elements, false otherwise
     */
    @Override
    public boolean isEmpty() {
        return nelems == 0;
    }

    /**
     * Remove the element from position index in the list
     *
     * @param index an integer that specifies at what index to remove an element from
     * @return Returns the data at the specified index (Type T)
     * @throws IndexOutOfBoundsException Exception thrown if index is outside the range
     * [0, size - 1]
     */
    @Override
    public T remove(int index) throws IndexOutOfBoundsException {
        // throw exception if index is out of bounds
        if (index < 0 || index >= size()) {
            throw new IndexOutOfBoundsException();
        }

        T toRemove;

        if (index == 0) { // if removing from the beginning
            toRemove = head.getNext().getElement();
            Node after = head.getNext().getNext();
            head.setNext(after);
            after.setPrev(head);
        } else if (index == size() - 1) { // if removing from the end
            toRemove = tail.getPrev().getElement();
            Node before = tail.getPrev().getPrev();
            before.setNext(tail);
            tail.setPrev(before);
        } else { // otherwise...
            Node now = head.getNext();
            for (int i = 0; i < index; i++) {
                now =  now.getNext();
            }
            toRemove = now.getElement();
            Node beforeToRemove = now.getPrev();
            Node after = now.getNext();

            beforeToRemove.setNext(after);
            after.setPrev(beforeToRemove);
        }
        nelems--;
        return toRemove;
    }


    /**
     * Set the value of an element at a certain index in the list.
     * @param index An integer that specifies at which node to alter the data
     * @param element Specifies the element (type T)
     * @return Returns the data previously at the specified position (type T)
     * @throws IndexOutOfBoundsException Exception thrown if index is outside the range
     * [0, size - 1]
     * @throws NullPointerException Exception thrown if data received is null
     */
    @Override
    public T set(int index, T element)
            throws IndexOutOfBoundsException, NullPointerException {

        //Throws exception if index is out of bounds
        if (index < 0 || index >= size()) {
            throw new IndexOutOfBoundsException();
        }
        // Throw exception if data is null
        if (element == null) {
            throw new NullPointerException();
        }
        Node n = getNth(index);
        T d = n.data;
        n.data = element;
        return d;
    }

    /**
     * Retrieves the amount of elements that are currently on the list.
     *
     * @return Return the number of elements stored in the list (an int)
     */
    @Override
    public int size() {
        return nelems;
    }

    /**
     * String representation of this list in the form of:
     * "[(head) -> elem1 -> elem2 -> ... -> elemN -> (tail)]"
     *
     * @return Return a String representation of the list
     */
    @Override
    public String toString() {
        StringBuilder s = new StringBuilder("[(head) -> ");
        Node n = head.getNext();
        // string representation implementation
        while (n != tail) {
            s.append(n.data).append(" -> ");
            n = n.next;
        }
        s.append("(tail)]");
        return s.toString();
    }


    /**
     * Remove nodes whose index is a multiple of base
     *
     * @param base Remove multiples of base
     */
    public void removeMultipleOf(int base) {
        for (int i = 0; i < size(); i += base) {
            this.remove(i);
        }
    }

    /**
     * Swap the nodes between index [0, splitIndex] of two lists
     *
     * @param other other DLL with which to swap elements
     * @param splitIndex Index up to which to swap elements
     */
    public void swapSegment(DoublyLinkedList other, int splitIndex) {
        T temp;
        T temp2;
        for (int i = 0; i <= splitIndex; i++) {
            temp = this.remove(i);
            temp2 = (T) other.remove(i);

            this.add(i, temp2);
            other.add(i, temp);
        }
    }

}
