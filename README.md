# python-student-management-system
Beginner-friendly Python Student Management System project using functions, file handling, lists, exception handling, and Object-Oriented Programming concepts.
# Student Management System

students = []

# Add Student
def add_student():
    try:
        name = input("Enter Student Name: ")
        marks = int(input("Enter Student Marks: "))

        student = {
            "name": name,
            "marks": marks
        }

        students.append(student)

        print("Student added successfully!")

    except ValueError:
        print("Invalid input! Marks should be numbers.")


# View Students
def view_students():

    if len(students) == 0:
        print("No student records found.")

    else:
        print("\nStudent Records:")

        for i, student in enumerate(students, start=1):
            print(i, "Name:", student["name"],
                  "| Marks:", student["marks"])


# Search Student
def search_student():

    search_name = input("Enter student name to search: ")

    found = False

    for student in students:

        if student["name"].lower() == search_name.lower():
            print("Student Found:")
            print("Name:", student["name"])
            print("Marks:", student["marks"])

            found = True
            break

    if not found:
        print("Student not found.")


# Delete Student
def delete_student():

    delete_name = input("Enter student name to delete: ")

    for student in students:

        if student["name"].lower() == delete_name.lower():
            students.remove(student)

            print("Student deleted successfully!")
            return

    print("Student not found.")


# Main Menu
while True:

    print("\n===== Student Management System =====")
    print("1. Add Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Delete Student")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()

    elif choice == "2":
        view_students()

    elif choice == "3":
        search_student()

    elif choice == "4":
        delete_student()

    elif choice == "5":
        print("Exiting program...")
        break

    else:
        print("Invalid choice! Please try again.")
