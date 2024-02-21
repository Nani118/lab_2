class Employee:
    def __init__(self, emp_id, name, age, salary):
        self.emp_id = emp_id
        self.name = name
        self.age = age
        self.salary = salary

class EmployeeTable:
    def __init__(self):
        self.employees = []

    def add_employee(self, employee):
        self.employees.append(employee)

    def display_table(self):
        for employee in self.employees:
            print(f"{employee.emp_id}\t{employee.name}\t{employee.age}\t{employee.salary}")

    def sort_table(self, sort_option):
        if sort_option == 1:  # Sort by Age
            self.employees.sort(key=lambda x: x.age)
        elif sort_option == 2:  # Sort by Name
            self.employees.sort(key=lambda x: x.name)
        elif sort_option == 3:  # Sort by Salary
            self.employees.sort(key=lambda x: x.salary)
        else:
            print("Invalid sorting option")

# Example usage
if __name__ == "__main__":
    table = EmployeeTable()

    table.add_employee(Employee("161E90", "Ramu", 35, 59000))
    table.add_employee(Employee("171E22", "Tejas", 30, 82100))
    table.add_employee(Employee("171G55", "Abhi", 25, 100000))
    table.add_employee(Employee("152K46", "Jaya", 32, 85000))

    print("Original Table:")
    table.display_table()

    sorting_option = int(input("Enter sorting option (1. Age, 2. Name, 3. Salary): "))
    table.sort_table(sorting_option)

    print("\nSorted Table:")
    table.display_table()
