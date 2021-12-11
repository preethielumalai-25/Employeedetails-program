# Employeedetails-program

from csv import reader


def get_data(name):
    with open('EmployeeSalaryData.csv', 'r') as read_obj:
        csv_reader = reader(read_obj)
        header = next(csv_reader)
        if header != None:
            for row in csv_reader:
                row_name = row[0]
                if row_name.split(',')[0] == name:
                    return row
                elif row_name.split(',')[1].strip() == name:
                    return row


name = input('Enter the name: ').upper()

data = get_data(name)

print(data)
