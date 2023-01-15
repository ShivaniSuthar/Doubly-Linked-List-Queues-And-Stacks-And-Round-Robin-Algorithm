import org.junit.Before;
import org.junit.Test;

import static org.junit.Assert.*;

public class DLLStackTest {

    DLLStack<Character> stack;

    @Before
    public void setUp() throws Exception {
        stack = new DLLStack<>();
    }

    @Test
    public void size() {
        assertEquals(0, stack.size());
        stack.push('S');
        assertEquals(1, stack.size());
        stack.pop();
        assertEquals(0, stack.size());
    }

    @Test
    public void isEmpty() {
        assertTrue(stack.isEmpty());
        stack.push('H');
        assertFalse(stack.isEmpty());
        stack.pop();
        assertTrue(stack.isEmpty());
    }

    @Test
    public void push() {
        stack.push('I');
        stack.push('V');
        assertEquals(2, stack.size());
        assertEquals(Character.valueOf('V'), stack.peek());
        assertFalse(stack.isEmpty());
    }

    @Test
    public void pop() {
        assertNull(stack.pop());
        stack.push('A');
        stack.push('N');
        assertEquals(Character.valueOf('N'), stack.pop());
        assertEquals(1, stack.size());
    }

    @Test
    public void peek() {
        assertNull(stack.peek());
        stack.push('I');
        assertNotNull(stack.peek());
        assertEquals(Character.valueOf('I'), stack.pop());
        assertNull(stack.peek());
    }
}
