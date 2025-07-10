# to_do_list
tasks = []

while True:
    print("\nTo-Do List Menu:")
    print("1. Add a task")
    print("2. Remove a task")
    print("3. View tasks")
    print("4. Quit")

    choice = input("Choose an option (1-4): ")

    if choice == '1':
        task = input("Enter a new task: ")
        tasks.append(task)
        print(f"Added task: {task}")
    elif choice == '2':
        if not tasks:
            print("Your to-do list is empty. Nothing to remove,")
        else:
            print("Your tasks:")
            for i, task in enumerate(tasks, start=1):
                print(f"{i}. {task}")
            task_num = input("Enter the task number to remove: ")
            if task_num.isdigit():
                task_index = int(task_num) - 1
                if 0 <= task_index < len(tasks):
                    removed_task = tasks.pop(task_index)
                    print(f"Removed task: {removed_task}")
                else:
                    print("Invalid task number.")
            else:
                print("Please enter a valid number.")
    elif choice == '3':
        if not tasks:
            print("Your to-do list is empty.")
        else:
            print("Your tasks:")
            for i, task in enumerate(tasks, start=1):
                print(f"{i}. {task}")

    elif choice == '4':
        print("Goodbye!")
        break
    else:
        print("Invalid choice, try again.")
