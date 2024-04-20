class TodoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print("Task added successfully!")

    def view_tasks(self):
        if self.tasks:
            print("Your to-do list:")
            for index, task in enumerate(self.tasks, 1):
                print(f"{index}. {task}")
        else:
            print("Your to-do list is empty!")

    def complete_task(self, task_index):
        if 1 <= task_index <= len(self.tasks):
            print(f"Task '{self.tasks[task_index - 1]}' marked as completed.")
            del self.tasks[task_index - 1]
        else:
            print("Invalid task index!")


def main():
    todo_list = TodoList()

    while True:
        print("\n1. Add Task\n2. View Tasks\n3. Complete Task\n4. Quit")
        choice = input("Enter your choice: ")

        if choice == "1":
            task = input("Enter task: ")
            todo_list.add_task(task)
        elif choice == "2":
            todo_list.view_tasks()
        elif choice == "3":
            task_index = int(input("Enter task number to mark as completed: "))
            todo_list.complete_task(task_index)
        elif choice == "4":
            print("Exiting program...")
            break
        else:
            print("Invalid choice. Please try again.")


if __name__ == "__main__":
    main()
