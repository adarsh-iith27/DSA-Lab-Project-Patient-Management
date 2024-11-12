Clinic Patient Management System
This program simulates a basic patient management system for a clinic. It allows clinic staff to manage patient records, categorize patients based on urgency, and interact with the data through a simple command-line interface. The system supports adding new patients, listing all patients, viewing the current queue, and searching patients by their mobile number.

Features
Add Patient: Enter details about a new patient, including their name, age, gender, blood type, medical problem, emergency status, and mobile number. The patient data is saved to a file (patients.csv) and added to either an emergency or regular queue based on their emergency status.
Take Patient to Doctor: Take the next available emergency patient or, if none exist, the next regular patient to see the doctor.
List All Patients: Display a list of all patients in the clinic, with separate lists for emergency patients and regular patients.
List Current Queue: Show the current queue of patients, prioritizing emergency cases.
Search by Mobile Number: Search for a patient by their mobile number and display their details if found.
File Persistence: Patient data is stored in a CSV file (patients.csv) to persist between program runs.
Code Breakdown
Classes
patient
This class represents a patient and contains the following member variables:

firstname: First name of the patient.
lastname: Last name of the patient.
blood: Blood type of the patient (e.g., A+, O-).
problem: The patient's medical issue or complaint.
number: Mobile number of the patient (used for searching).
age: Age of the patient.
gender: Gender of the patient (m/f/o).
emergency: A boolean indicating if the patient is in an emergency situation.
Constructors:
Default constructor initializes the attributes with default values.
Parameterized constructor allows setting all attributes at once.
patientqueue
This class manages patient queues and data:

Member Variables:
patients: Queue for regular patients.
emergencypatients: Queue for emergency patients.
patientMap: A hash map to store patient details using their mobile number for fast look-up.
Member Functions:
saveToFile(patient p): Saves a patient’s data to patients.csv in a CSV format.
loadFromFile(): Loads patient data from the CSV file and populates the queues and patient map.
addpatient(): Allows the user to add a new patient to the system by entering their details.
takepatienttodoctor(): Takes the next patient (starting with emergency patients) to the doctor.
displayPatient(patient p): Displays detailed information about a patient.
patientlist(): Displays all patients, categorizing them into emergency and regular patients.
listcurrentqueue(): Displays the current patient queue with the priority given to emergency patients.
searchmobile(long long number): Searches for a patient by their mobile number and displays their information if found.
How to Use
Menu Options
The system provides a text-based menu for interacting with the program:

Add Patient: Add a new patient with details like name, blood type, problem, and emergency status.
Take Patient to Doctor: Take the next emergency patient or, if there are no emergencies, a regular patient.
Display List of All Patients: Show all patients in the clinic, divided into emergency and regular patients.
Show Current Queue: List the current queue of patients with emergency patients shown first.
Search Patient by Mobile Number: Find and display a patient's details by entering their mobile number.
Exit: Exit the program.
Sample Input/Output
When the program is running, you will see the following options presented as a menu:

css
Copy code
----Welcome----

CLINIC MENU
[1] Add patient
[2] Take patient to Doctor
[3] Display list of all patients
[4] Show current queue
[5] Search patient by mobile number
[6] Exit
Please enter your choice: 1
If you choose 1 to add a patient, the program will prompt you for the following details:

mathematica
Copy code
Enter Patient details
First Name: John
Last Name: Doe
Blood Group (A+, A-, B+, B-, O+, O-, AB+, AB-): O+
Gender (m/f/o): m
Age: 30
Mobile Number: 1234567890
Emergency? (1 for yes, 0 for no): 0
What's troubling you?: Fever
After you enter the details, the program will save the patient to the queue and the CSV file.

File Persistence
Patient data is saved to a file named patients.csv. This file stores the following fields:

Patient's mobile number
First name
Last name
Blood type
Age
Gender
Medical problem
Emergency status (0 or 1)
Example of a line in the file:

mathematica
Copy code
1234567890,John,Doe,O+,30,m,Fever,0
Error Handling
If the program cannot open the file (patients.csv) for reading or writing, it will display an error message.
Invalid input, such as entering an incorrect blood group or age, will prompt the user to try again.
Compilation and Execution
Save the code in a file named clinic.cpp.

Compile the code using a C++ compiler:

Copy code
g++ -o clinic clinic.cpp
Run the executable:

bash
Copy code
./clinic
Follow the on-screen instructions to interact with the program.

License
This program is provided for educational purposes. Feel free to modify and enhance it as needed.