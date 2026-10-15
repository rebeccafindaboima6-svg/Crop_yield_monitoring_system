# Crop Yield Monitoring System

## 1. Project Description

The Crop Yield Monitoring System is a Python application developed for the PROG211 Object-Oriented Programming 1 assignment. The system helps users record farmer information, manage crop records, and monitor crop yield performance.

It allows users to enter crop details, record expected and actual yields, display saved records, and view the total number of records created during a program session.

## 2. Project Objectives

The main objectives of this project are to:

- Apply object-oriented programming concepts in Python.
- Store and manage farmer and crop information.
- Calculate crop yield performance as a percentage.
- Validate farm size and yield inputs.
- Display crop records in a clear and organized format.

## 3. System Features

- Add new crop records.
- Enter farmer ID, name, and location.
- Record crop name and farm size.
- Enter expected and actual crop yields.
- Calculate yield performance automatically.
- Display crop records.
- Show the total number of crop records.
- Validate numeric inputs and prevent negative yield values.
- Exit the program through the menu.

## 4. Object-Oriented Programming Concepts

The project demonstrates the following concepts:

**Classes and Objects:** The `Farmer` class stores farmer details, while the `CropRecord` class stores crop information and manages yield calculations.

**Constructor:** The `__init__()` methods initialize the attributes of each object.

**Instance Methods:** Methods such as `display_info()`, `calculate_performance()`, and `update_record()` perform operations on objects.

**Class Method:** The `get_total_records()` method returns the number of crop record objects created during the current program session.

**Static Method:** The `is_valid_yield()` method checks whether a yield amount is zero or greater.

**Encapsulation:** Related data and operations are organized within their respective classes.

## 5. Technologies Used

- **Programming Language:** Python 3
- **Development Environment:** PyCharm
- **Version Control and Hosting:** GitHub

## 6. How to Run the Program

1. Download or clone this repository to your computer.
2. Open the project in PyCharm or another Python editor.
3. Open `crop_yield_monitoring_system.py`.
4. Run the Python file.
5. Select an option from the menu.
6. Follow the instructions displayed in the console.

## 7. Example Usage

Example input for a crop record:

- Record ID: 1
- Farmer ID: F001
- Farmer Name: John Kamara
- Farm Location: Bo
- Crop Name: Rice
- Farm Size: 2 acres
- Expected Yield: 1000 kg
- Actual Yield: 800 kg

**Expected result:**

Yield Performance: 80.00%

The system calculates yield performance using the formula:

Yield Performance = (Actual Yield / Expected Yield) × 100

Therefore, (800 / 1000) × 100 = 80%.

## 8. Data Storage and Limitations

The system stores crop records in memory while it is running. The records are not permanently saved to a database or file. When the program is restarted, the records and total record count reset.

## 9. Conclusion

The Crop Yield Monitoring System demonstrates how Python and object-oriented programming can be used to organize farmer information, manage crop records, validate input, and calculate crop yield performance. The project provides practical experience with classes, objects, methods, and basic data management.

## 10. Assignment Alignment

This project was developed for the PROG211 Object-Oriented Programming 1 assignment under the topic of Agriculture: Crop Yield Monitoring System. The Python source code and program execution screenshots provide evidence of the system's implementation and functionality.
