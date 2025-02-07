import json
import os

TASKS_FILE = "tasks.json"

def load_tasks():
    if os.path.exists(TASKS_FILE):
        with open(TASKS_FILE, 'r') as file:
            return json.load(file)
    return []

def save_tasks(tasks):
    with open(TASKS_FILE, 'w') as file:
        json.dump(tasks, file, indent=4)

def add_task(tasks):
    task = input("أدخل المهمة الجديدة: ")
    tasks.append(task)
    save_tasks(tasks)
    print("تمت إضافة المهمة بنجاح.")

def view_tasks(tasks):
    if not tasks:
        print("لا توجد مهام حالياً.")
    else:
        print("المهام الحالية:")
        for index, task in enumerate(tasks, start=1):
            print(f"{index}. {task}")

def delete_task(tasks):
    view_tasks(tasks)
    task_number = int(input("أدخل رقم المهمة التي تريد حذفها: ")) - 1
    if 0 <= task_number < len(tasks):
        deleted_task = tasks.pop(task_number)
        save_tasks(tasks)
        print(f"تم حذف المهمة: {deleted_task}")
    else:
        print("رقم المهمة غير صالح.")

def main():
    tasks = load_tasks()
    while True:
        print("\nمدير المهام اليومية")
        print("1. إضافة مهمة")
        print("2. عرض المهام")
        print("3. حذف مهمة")
        print("4. الخروج")
        choice = input("أدخل اختيارك: ")
        if choice == '1':
            add_task(tasks)
        elif choice == '2':
            view_tasks(tasks)
        elif choice == '3':
            delete_task(tasks)
        elif choice == '4':
            break
        else:
            print("اختيار غير صالح. حاول مرة أخرى.")

if __name__ == "__main__":
    main()
