# Java8-master

Author : Srinivasa Duggempudi.

### Table of Contents                       
| No. | Questions |
|---- | ---------
|1 | [Custom Stack Implementation?](#custom-stack-implementation)|
|2 | [What is the difference between AngularJS and Angular?](#what-is-the-difference-between-angularjs-and-angular)|
|3 | [What is TypeScript?](#what-is-typescript)|
|4 | [Write a pictorial diagram of Angular architecture?](#write-a-pictorial-diagram-of-angular-architecture)|
|5 | [What are the key components of Angular?](#what-are-the-key-components-of-angular)|
|6 | [What are directives?](#what-are-directives)|


1. ### Custom Stack Implementation?

    **Stack :** Stack is a linear data structure in which insertion and deletion are done at one end, called as top.
               The last element inserted is the first one to be deleted. Hence, it is called Last in First Out(LIFO) or First in Last Out(FILO) list,
               
   **Stack Operations**
   
      **1.push():** Insert the data in the stack.
      
      **2.pop():**  Removes and returns the last inserted element from the stack.
      
      **3.peek():** Returns the last inserted element without removing it.
    
    **Implementation**
     Take the three variable like top, array and capacity.
     
     ```
       public class Stack {
	int top ;
	int arr[];
	int capacity;
	
	public Stack(int size) {
		this.top = -1;
		this.arr = new int[size];
		this.capacity = size;
	}
     
     ```
     **push:**  here before adding the element to array increase the array index(top) and assign the value. 
     
    ```
      public void push(int x) {
		
		if(!isFull()) {
			top = top +1;
			arr[top] =x;
		}else {
			
			System.out.println("Stack is Full");
		}
	}
    ```
    
      **POP :**  Take the top index element of array to return and reduce the top index value.
      
      ```
        public int pop() {
		
		int element = arr[top];
		top = top-1;
		return element ;

	}
      ```
    **PEEK:**  Pick and return the top element of Array,
    
    ```
      public int peek() {
		if(isEmpty()) {
			System.out.println("Stack is Empty");
		}
		return arr[top];
	}
    
    ```
    **COMPLETE CODE :**
   
    ```
     
       public class Stack {
	int top ;
	int arr[];
	int capacity;
	
	public Stack(int size) {
		this.top = -1;
		this.arr = new int[size];
		this.capacity = size;
	}
	
	public boolean isFull() {
		return top == capacity-1;
	}
	
	public void push(int x) {
		
		if(!isFull()) {
			top = top +1;
			arr[top] =x;
		}else {
			
			System.out.println("Stack is Full");
		}
	}
              
	      public int pop() {
		
		int element = arr[top];
		top = top-1;
		return element ;
	}
	
	public int peek() {
		if(isEmpty()) {
			System.out.println("Stack is Empty");
		}
		return arr[top];
	}

	public boolean isEmpty() {
		return top==-1;
	}
	public int size() {
		return top+1;
	}
          }
	  
    ```
     **Main method **
     
     ```
       package datastractures.stack;

         public class StackDemo {

	public static void main(String[] args) {
		Stack stack = new Stack(3);
		 
        stack.push(1);      // inserting 1 in the stack
        stack.push(2);      // inserting 2 in the stack
 
        stack.pop();        // removing the top element (2)
        stack.pop();        // removing the top element (1)
 
        stack.push(3);      // inserting 3 in the stack
 
        System.out.println("The top element is " + stack.peek());
        System.out.println("The stack size is " + stack.size());
 
        stack.pop();        // removing the top element (3)
 
        // check if the stack is empty
        if (stack.isEmpty()) {
            System.out.println("The stack is empty");
        }
        else {
            System.out.println("The stack is not empty");
          }
         }
       }
