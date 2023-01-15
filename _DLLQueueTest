import org.junit.Before;
import org.junit.Test;

import static org.junit.Assert.*;

public class DLLQueueTest {

    DLLQueue<Character> testQueue;

    @Before
    public void setUp() {
        testQueue = new DLLQueue<>();
    }

    @Test
    public void size() {
        assertEquals(0, testQueue.size());
        testQueue.enqueue('S');
        assertEquals(1, testQueue.size());
        testQueue.dequeue();
    }

    @Test
    public void isEmpty() {
        assertTrue(testQueue.isEmpty());
        testQueue.enqueue('H');
        assertFalse(testQueue.isEmpty());
        testQueue.dequeue();
        assertTrue(testQueue.isEmpty());
    }

    @Test
    public void enqueue() {
        testQueue.enqueue('I');
        testQueue.enqueue('V');
        assertEquals(Character.valueOf('I'), testQueue.peek());
        assertEquals(2, testQueue.size());
        assertFalse(testQueue.isEmpty());
    }

    @Test
    public void dequeue() {
        assertNull(testQueue.dequeue());
        testQueue.enqueue('A');
        testQueue.enqueue('N');
        assertEquals(Character.valueOf('A'), testQueue.dequeue());
        assertEquals(1, testQueue.size());
    }

    @Test
    public void peek() {
        assertNull(testQueue.peek());
        testQueue.enqueue('I');
        assertNotNull(testQueue.peek());
        assertEquals(Character.valueOf('I'), testQueue.dequeue());
        assertNull(testQueue.peek());
    }
}
