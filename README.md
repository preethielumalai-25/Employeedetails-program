# Employeedetails-program

Project Descriptions 
Language : Python 

Create a project going through the process of collection of 5000 records of employees taken from HR department of an organization and apply principles of oops to create a program taking 5 different departments from an organization and validate if at least 10 records of employee get matched with their required departments. 


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


OUTPUT :
Enter the name: aaron
['AARON,  JEFFERY M', 'SERGEANT', 'POLICE', '$1,01,442', '09/26/2005', '06-01-2016', 'SALARY', 'Fulltime-Regular']
