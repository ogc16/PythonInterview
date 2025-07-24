```
 class ListNode:
    def __init__(self, data: int):
        self.data = data
        self.next = None


class Problem13:
    def reverseLinkedList(self, head: ListNode) -> ListNode:
        if not head or not head.next:
            # List is empty or contains only one node, return as is
            return head

        prev_node = None
        current_node = head

        while current_node:
            next_node = current_node.next
            current_node.next = prev_node
            prev_node = current_node
            current_node = next_node

        return prev_node


def printLinkedList(head: ListNode):
    if not head:
        print("List is empty")
        return

    while head:
        print(head.data, end=" ")
        head = head.next
    print()


def main():
    try:
        head = ListNode(1)
        head.next = ListNode(2)
        head.next.next = ListNode(3)
        head.next.next.next = ListNode(4)
        head.next.next.next.next = ListNode(5)

        print("Original Linked List:")
        printLinkedList(head)

        problem = Problem13()
        head = problem.reverseLinkedList(head)

        print("Reversed Linked List:")
        printLinkedList(head)
    except Exception as e:
        print(f"An error occurred: {str(e)}")


if __name__ == "__main__":
    main()
```
