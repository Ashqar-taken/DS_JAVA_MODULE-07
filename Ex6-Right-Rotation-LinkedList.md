# Ex6 Right Rotation LinkedList
## DATE: 30.08.2026

## AIM:

To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.

## Algorithm
1. Import the necessary libraries.
2. Create a linkedlist by defining the required methods such as insert, display.
3. Obtain the elements to insert into LinkedList from user.
4. Input the number of times to rotate the linked list.
5. Define a method to rotate linkedlist.
6. Display the rotated list.

## Program:
```
/*
Program to  Right Rotation LinkedList
Developed by: Ashqar Ahamed S T 
RegisterNumber: 212224240018
*/

import java.util.Scanner;
public class RotateLinkedList {
    public static Node rotate(Node head, int k) {
        
        for(int i=0;i<k;i++)
        {
            Node temp2 = head;
            Node prev = null;
            while(temp2.next!=null)
            {
                prev = temp2;
                temp2 = temp2.next;
            }
            prev.next = null;
            temp2.next = head;
            head = temp2;
        }
        return head;
       
       
    }
    public static void display(Node head) {
        Node current = head;
        System.out.print("LinkedList: ");
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
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
        int k = scanner.nextInt();
        head = rotate(head, k);
        display(head);
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

<img width="992" height="218" alt="output Day1" src="https://github.com/user-attachments/assets/a4bb9525-611a-4aac-b37b-eb65b550f58c" />


## Result:
Thus, the java program to perfom right rotation on linked list is implemented successfully.
