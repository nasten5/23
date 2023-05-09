HomeWork2
index + ", Size: " + size);
}

if (index == 0) {
removeFirst();
} else if (index == size - 1) {
removeLast();
} else {
Node current = head;

for (int i = 1; i < index; i++) {
current = current.getNext();
}

current.setNext(current.getNext().getNext());
size–;
}
}

// получение элемента по указанному индексу
public int get(int index) {
if (index < 0 || index >= size) {
throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
}

Node current = head;

for (int i = 0; i < index; i++) {
current = current.getNext();
}

return current.getValue();
}

// размер списка
public int size() {
return size;
}

// вывод всего списка на экран
public void printList() {
Node current = head;

while (current != null) {
System.out.print(current.getValue() + " ");
current = current.getNext();
}

System.out.println();
}

private static class Node {
private int value;
private Node next;

public Node(int value, Node next) {
this.value = value;
this.next = next;
}

public int getValue() {
return value;
}

public void setValue(int value) {
this.value = value;
}

public Node getNext() {
return next;
}

public void setNext(Node next) {
this.next = next;
}
}
}
