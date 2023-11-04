# CSE15L Lab 3

**Part 1 -- Bugs** <br>

Code for JUnit test that induced a failure: <br>
```
public class LinkedListTests {
	@Test 
	public void testAppend() {
    LinkedList link = new LinkedList();
    
    link.append(1);
    link.append(2);
    link.append(3);

    assertEquals(3, link.last());
	}
}

```
Code for JUnit test that does not induce a failure: <br>

```
public class LinkedListTests {
	@Test 
	public void testAppend() {
    LinkedList link = new LinkedList();
    
    link.append(1);
    link.append(2);

    assertEquals(2, link.last());
	}
}
```
The Symptom: <br>
![Image](2_test_JUnit.png) <br>

The Bug: <br>

  Before fix:
  ```
  while(n.next != null) {
              n = n.next;
              n.next = new Node(value, null);
          }
  ```

  After fix:
  ```
  while(n.next != null) {
              n = n.next;
          }
           n.next = new Node(value, null);
  ```
  
  The issue was in the LinkedListExample file, specifically with the append() method. While the method works fine when the linkedlist had zero or one element, when trying to append with the list having two elements already, the while loop would run forever, since it is stopping at n.next = null. With the n.next = new Node(value,null) line inside the while loop, the n.next will never be null, thus running forver and inducing the OutOfMemoryError as it is an infinite loop.
  To address the issue, the line n.next = new Node(value, null) was moved outside the while loop, so that it does the intended function of adding the new node that takes value to the end of the list. This way the while loop stops at the last element.



**Part 2 -- Researching Commands** <br>

Path to Private Key: <br>
![Image](Private_Key.png) <br>

Path to Public Key: <br>
![Image](Public_Key.png) <br>

Login without password: <br>
![Image](Login No Pass.png) <br>

