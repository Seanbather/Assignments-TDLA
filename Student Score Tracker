

import os

FILENAME = "students.txt"

# Load records from file
def load_data():
    students = {}
    if os.path.exists(FILENAME):
        with open(FILENAME, "r") as file:
            for line in file:
                name, score = line.strip().split(",")
                students[name] = float(score)
    return students

# Save records to file
def save_data(students):
    with open(FILENAME, "w") as file:
        for name, score in students.items():
            file.write(f"{name},{score}\n")

# Add student
def add_student(students):
    name = input("Enter student name: ")
    score = float(input("Enter score: "))
    students[name] = score
    print("Student added successfully!")

# View all students
def view_students(students):
    if not students:
        print("No records found.")
    else:
        print("\nStudent Scores:")
        for name, score in students.items():
            print(f"{name}: {score}")

# Update student score
def update_student(students):
    name = input("Enter student name to update: ")
    if name in students:
        score = float(input("Enter new score: "))
        students[name] = score
        print("Score updated successfully!")
    else:
        print("Student not found.")

# Delete student
def delete_student(students):
    name = input("Enter student name to delete: ")
    if name in students:
        del students[name]
        print("Student deleted successfully!")
    else:
        print("Student not found.")

# Calculate statistics
def calculate_stats(students):
    if not students:
        print("No data to calculate.")
        return

    scores = list(students.values())
    average = sum(scores) / len(scores)
    highest = max(scores)
    lowest = min(scores)

    print(f"Average Score: {average:.2f}")
    print(f"Highest Score: {highest}")
    print(f"Lowest Score: {lowest}")

# Main menu
def main():
    students = load_data()

    while True:
        print("\n--- Student Score Tracker ---")
        print("1. Add Student")
        print("2. View Students")
        print("3. Update Student Score")
        print("4. Delete Student")
        print("5. Calculate Statistics")
        print("6. Save & Exit")

        choice = input("Enter choice: ")

        if choice == "1":
            add_student(students)
        elif choice == "2":
            view_students(students)
        elif choice == "3":
            update_student(students)
        elif choice == "4":
            delete_student(students)
        elif choice == "5":
            calculate_stats(students)
        elif choice == "6":
            save_data(students)
            print("Data saved. Goodbye!")
            break
        else:
            print("Invalid choice. Try again.")

# Run program
main()