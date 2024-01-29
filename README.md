class ToDoList:
    def __init__(self, lst_name, lst_items) -> None:
        self.lst_name = lst_name
        self.lst_items = lst_items

    def display_list(self):
        for i in range(0, len(self.lst_items)):
            print(f"Task: {self.lst_items[i][0]} , Status: {self.lst_items[i][1]}")


option = input(
    "Would you like to:\n1) Make a To-do List\nEnter the corresponding number: "
)
while True:
    if option.isdigit():
        option = int(option)
        if option in [1]:
            break
        else:
            option = input("Not within range!\nTry again: ")
    else:
        option = input("Invalid input!\nTry again: ")

if option == 1:
    lst_name = input("Enter a name for your list: ")
    tasks = input("Enter the number of tasks: ")
    while not (tasks.isdigit()):
        tasks = input("Invalid input!\nTry again: ")
    lst_items = []
    for i in range(int(tasks)):
        item_task = input("Enter a task: ")
        item_status = input("Enter the task status (T/F): ")
        while item_status.lower() not in ["f", "t", "true", "false"]:
            item_status = input("Invalid input!\nTry again: ")
        lst = [item_task, item_status]
        lst_items.append(lst)
    instance = ToDoList(lst_name, lst_items)
    instance.display_list()
