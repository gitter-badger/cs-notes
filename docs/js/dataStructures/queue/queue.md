# Queue

> A queue is a FIFO (first-in-first-out) data structure, in which the first element is inserted from one end called the REAR (also called tail), and the removal of existing element takes place from the other end called as FRONT (also called head).

![](queue.png)

<p style="color: #888888; text-align: center; margin-top: -20px;">Source: <a href="https://en.wikipedia.org/wiki/Queue_(abstract_data_type)">Wikipedia</a></p>

#### Summary

- Queues are useful for processing tasks and are foundational for more complex data structures.
- Insertion and Removal can be done in O(1).

#### Implementation

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class Queue {
  constructor() {
    this.first = null;
    this.last = null;
    this.size = 0;
  }

  enqueue(value) {
    var newNode = new Node(value);
    if (!this.first) {
      this.first = newNode;
      this.last = newNode;
    } else {
      this.last.next = newNode;
      this.last = newNode;
    }
    return ++this.size;
  }

  dequeue() {
    if (!this.first) return null;
    var temp = this.first;
    if (this.size === 1) {
      this.last = null;
    }
    this.first = this.first.next;
    this.size--;
    return temp.value;
  }
}
```
