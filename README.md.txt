# Crop Yield Monitoring System

Description:
Crop Yield Monitoring System is a Python console program for monitoring crop yield. It records farmer name, crop name, farm size, expected yield and actual yield. The system calculates performance to check farm productivity.

OOP Concepts Used:
1. Class and Object - CropRecord class for single record and CropYieldSystem class for managing records
2. Constructor - _init_ method used to initialize attributes
3. Encapsulation - Attributes are kept private inside class
4. Methods - add_record(), calculate_performance(), display_records() to perform operations

Features:
- Add crop records with details
- Calculate yield performance using (Actual Yield / Expected Yield * 100)
- Display all records
- Menu driven system with 3 options
- Input validation

How to Run:
1. Make sure Python is installed
2. Open terminal
3. Run: python Crop_Yield_Monitoring_System.py
4. Choose from menu:
   1 - Add Crop Record
   2 - Display Records
   3 - Exit

Example:
Expected Yield = 100
Actual Yield = 75
Performance = 75%
If performance is 100% and above, yield is good. If below 100%, yield is low.