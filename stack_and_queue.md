# Stacks and Queues

## What is a Stack

- A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.

Common terminology for a stack is

1. Push - Nodes or items that are put into the stack are pushed

2. Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.

3. Top - This is the top of the stack.

4. Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.

5. IsEmpty - returns true when stack is empty otherwise returns false.

### Stacks follow these concepts:

FILO
First In Last Out

This means that the first item added in the stack will be the last item popped out of the stack.

LIFO
Last In First Out

This means that the last item added to the stack will be the first item popped out of the stack.

## Stack Visualization

![stack visual.](./images/stackvis.png)

-  When you push something to the stack, it becomes the new top

- When you pop something from the stack, you pop the current top and set the next top as top.next

## stack methods:

### 1. push
- When adding a Node, you push it into the stack by assigning it as the new top, with its next property equal to the original top.


`newNode = stack.top`

- Next, you need to assign the next property of new Node  to reference the same Node that top is referencing

`newNode.next = top`

### 2. pop 

- Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node

### 3. peek 

- When conducting a peek, you will only be inspecting the top Node of the stack.

### 4. is empty

- returns a boolean 

## What is a Queue

### Common terminology for a queue is

1. Enqueue - Nodes or items that are added to the queue.
2. Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
3. Front - This is the front/first Node of the queue.
4. Rear - This is the rear/last Node of the queue.
5. Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
6. IsEmpty - returns true when queue is empty otherwise returns false.

- Queues follow these concepts:

FIFO
First In First Out

This means that the first item in the queue will be the first item out of the queue.

LILO
Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

## Queue Visualization

![queuevisu.](./images/Queuevis..png)

### Queue methods:

### 1. enqueue : 
When you add an item to a queue, you use the enqueue action. This is done with an O(1) operation in time because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

### 2. dequeue: 
When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.

### 3. peek : 
When conducting a peek, you will only be inspecting the front Node of the queue.

### 4. is empty:
returns a boolean 

