import org.junit.Before;
import org.junit.Test;

import static org.junit.Assert.*;

public class DoublyLinkedListTest {

    DoublyLinkedList<Integer> testDLL;
    DoublyLinkedList<Integer> testDLL2;

    @Before
    public void setUp() throws Exception {
        testDLL = new DoublyLinkedList<Integer>();
        testDLL2 = new DoublyLinkedList<Integer>();
    }

    @Test
    public void add() {
        testDLL.add(2);
        assertEquals(Integer.valueOf(2), testDLL.get(0));
        testDLL.add(6);
        testDLL.add(7);
        assertEquals(Integer.valueOf(6), testDLL.get(1));
        assertEquals(Integer.valueOf(7), testDLL.get(2));
    }

    @Test (expected = NullPointerException.class)
    public void addThrowsNPException() {
        testDLL.add(null);
    }

    @Test
    public void testAdd2() {
        testDLL.add(0, 6);
        assertEquals(Integer.valueOf(6), testDLL.get(0));
        testDLL.add(1, 10);
        assertEquals(Integer.valueOf(10), testDLL.get(1));
        testDLL.add(0, 20);
        assertEquals(Integer.valueOf(20), testDLL.get(0));
        assertEquals(Integer.valueOf(6), testDLL.get(1));
    }

    @Test (expected = NullPointerException.class)
    public void testAddThrowsNPException() {
        testDLL.add(0, null);
    }

    @Test (expected = IndexOutOfBoundsException.class)
    public void testAddThrowsIndexOutOfBoundsException() {
        testDLL.add(-100, 5);
    }

    @Test
    public void clear() {
        testDLL.add(0, 2);
        testDLL.add(1, 4);
        testDLL.add(2, 6);
        assertFalse(testDLL.isEmpty());
        testDLL.clear();
        assertEquals(0, testDLL.size());
        assertTrue(testDLL.isEmpty());
    }

    @Test
    public void contains() {
        testDLL.add(0, 6);
        assertTrue(testDLL.contains(6));
        assertFalse(testDLL.contains(11));
        testDLL.remove(0);
        assertFalse(testDLL.contains(6));
    }

    @Test
    public void get() {
        testDLL.add(5);
        testDLL.add(12);
        testDLL.add(13);
        assertEquals(Integer.valueOf(5), testDLL.get(0));
        assertEquals(Integer.valueOf(12), testDLL.get(1));
        assertEquals(Integer.valueOf(13), testDLL.get(2));
    }

    @Test (expected = IndexOutOfBoundsException.class)
    public void getThrowsIndexOutOfBoundsException() {
        testDLL.add(9);
        assertEquals(Integer.valueOf(9), testDLL.get(-1000));
    }

    @Test
    public void isEmpty() {
        assertTrue(testDLL.isEmpty());
        testDLL.add(19);
        testDLL.add(38);
        testDLL.add(57);
        assertFalse(testDLL.isEmpty());
        testDLL.clear();
        assertTrue(testDLL.isEmpty());
    }

    @Test
    public void remove() {
        testDLL.add(40);
        testDLL.add(80);
        testDLL.add(120);
        assertEquals(testDLL.size(), 3);
        testDLL.remove(2);
        assertEquals(testDLL.size(), 2);
        testDLL.remove(0);
        testDLL.remove(0);
        assertTrue(testDLL.isEmpty());
    }

    @Test (expected = IndexOutOfBoundsException.class)
    public void removeThrowsIndexOutOfBoundsException() {
        testDLL.add(19);
        testDLL.remove(4);
    }

    @Test
    public void set() {
        testDLL.add(5);
        testDLL.add(11);
        testDLL.add(17);
        testDLL.set(1, 13);
        assertEquals(Integer.valueOf(13), testDLL.get(1));
        testDLL.set(0, 13);
        testDLL.set(2, 13);
        assertEquals(Integer.valueOf(13), testDLL.get(0));
        assertEquals(Integer.valueOf(13), testDLL.get(2));
    }

    @Test (expected = IndexOutOfBoundsException.class)
    public void setThrowsIndexOutOfBoundsException() {
        testDLL.add(0);
        testDLL.set(1, 1);
    }

    @Test (expected = NullPointerException.class)
    public void setThrowsNPException() {
        testDLL.add(0);
        testDLL.set(0, null);
    }

    @Test
    public void size() {
        testDLL.add(11);
        assertEquals(testDLL.size(), 1);
        testDLL.add(14);
        assertEquals(testDLL.size(), 2);
        testDLL.add(9);
        assertEquals(testDLL.size(), 3);
    }

    @Test
    public void testToString() {
        assertEquals("[(head) -> (tail)]", testDLL.toString());
        testDLL.add(8);
        testDLL.add(10);
        testDLL.add(12);
        testDLL.add(21);
        assertEquals("[(head) -> 8 -> 10 -> 12 -> 21 -> (tail)]", testDLL.toString());
        testDLL.remove(3);
        assertEquals("[(head) -> 8 -> 10 -> 12 -> (tail)]", testDLL.toString());
    }

    @Test
    public void removeMultipleOf() {
        int[] vals = new int[]{0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

        for (int i : vals) {
            testDLL.add(i);
        }

        testDLL.removeMultipleOf(3);

        assertEquals(testDLL.size(), 8);
        assertEquals(Integer.valueOf(1), testDLL.get(0));
        assertEquals(Integer.valueOf(10), testDLL.get(7));
    }

    @Test
    public void swapSegment() {
        int[] first = new int[]{0, 1, 2, 3, 4};
        int[] second = new int[]{9, 8, 7, 6, 5, 4, 3};

        for (int i : first) {
            testDLL.add(i);
        }
        for (int j : second) {
            testDLL2.add(j);
        }

        testDLL.swapSegment(testDLL2, 2);

        assertEquals(Integer.valueOf(9), testDLL.get(0));
        assertEquals(Integer.valueOf(0), testDLL2.get(0));
        assertEquals(Integer.valueOf(7), testDLL.get(2));
        assertEquals(Integer.valueOf(2), testDLL2.get(2));
    }
}
