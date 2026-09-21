# Ex8 Detection of Cycle and Finding the Starting Node in a Linked List
## DATE: 03.08.2026
## AIM:
To write a program that detects a cycle in a linked list and returns the node where the cycle begins.
If there is no cycle, the program should return null without modifying the linked list.
## Algorithm
1. Import the necessary libraries.
2. Create a linkedlist by defining the required methods such as insert, display.
3. Obtain the elements to insert into LinkedList from user
4. Use the Floyd’s Cycle Detection Algorithm (also called the tortoise and hare algorithm).
5. To find if there is any cycle, return true if there is else false.
   

## Program:
```
/*
program that detects a cycle in a linked list and returns the node where the cycle begins.
If there is no cycle, the program should return null without modifying the linked list.
Developed by: Ashqar Ahamed S T
RegisterNumber: 212224240018 
*/

import java.util.Scanner;

public class DetectLoopFloyd {
    public static boolean hasLoop(Node head) {
        Node slow = head;
        Node fast = head;
        while(fast!=null && fast.next!=null)
        {
            slow = slow.next;
            fast = fast.next.next;
            
            if(slow == fast)
            {
                return true;
            }
        }
        
        return false;
        
       
       
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Node head = null, tail = null;

        int n = scanner.nextInt();

        for (int i = 0; i < n; i++) {
            Node newNode = new Node(scanner.nextInt());
            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }

      
        int pos = scanner.nextInt();

        if (pos > 0) {
            Node loopNode = head;
            for (int i = 1; i < pos && loopNode != null; i++) {
                loopNode = loopNode.next;
            }
            if (loopNode != null) {
                tail.next = loopNode;
            }
        }

        if (hasLoop(head)) {
            System.out.println("Loop detected in the LinkedList.");
        } else {
            System.out.println("No loop detected in the LinkedList.");
        }

        scanner.close();
    }
}

class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}


```

## Output:

<img width="983" height="240" alt="output Day3" src="https://github.com/user-attachments/assets/edbab8ec-fca6-4e2c-96df-027e1dad1bfd" />


## Result:
The program successfully detects whether a cycle exists in the linked list.
If a cycle is present, it correctly identifies and returns the node where the cycle begins.
