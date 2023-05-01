Download Link: https://assignmentchef.com/product/solved-cs211-assignment-2
<br>
Computerizing health records makes it easier for patients to share their health profiles and histories among their various health care professionals. Write a program that maintains computerized health records for several patients. This includes designing several classes: <em>HealthRecords, Patient, </em>and<em> Checkup</em>. All class attributes must be private and accessed through public member functions.




The attributes of each class are summarized below:




<em>HealthRecords</em> class has the following private attributes:

vector &lt;Patient&gt; patientsRecords;




<em>Patient </em>class has the following private attributes:

const long patientAccountNum;  // =nextPatientAccountNum  string firstName;

string lastName;

long SSN;

char gender;  string birthDate;

vector &lt;Checkup&gt; patientCheckups;

static long nextPatientAccountNum; // initialize it to 5000 and increment it by 2

// as you create a new object




<em>Checkup</em> class has at least the following private attributes:

<table width="429">

 <tbody>

  <tr>

   <td width="236">            string checkupDate;</td>

   <td width="193"> </td>

  </tr>

  <tr>

   <td width="236">            double height;</td>

   <td width="193">// in feet</td>

  </tr>

  <tr>

   <td width="236">                double weight;</td>

   <td width="193">// in pounds</td>

  </tr>

  <tr>

   <td width="236">                int cholesterol;</td>

   <td width="193">// total cholesterol</td>

  </tr>

  <tr>

   <td width="236">                int hdlCholesterol;</td>

   <td width="193">// HDL cholesterol</td>

  </tr>

  <tr>

   <td width="236">                int triglycerides;</td>

   <td width="193">// Triglycerides concentration</td>

  </tr>

  <tr>

   <td width="236">                int glucose;</td>

   <td width="193">// glucose level</td>

  </tr>

  <tr>

   <td width="236">            string bloodPressure;</td>

   <td width="193">// blood pressure</td>

  </tr>

 </tbody>

</table>




For each class, you need to write the following: an appropriate constructor, set and get functions as needed, and print functions to print the values of the attributes on the screen.  The main member functions for the <em>HealthRecords</em> class are summarized below.

<em> </em>

<ul>

 <li><em>void HealthRecords::createNewPatient (string fName, string lName, long pSSN, char gender, string birthDate); </em></li>

</ul>

<em> </em>

This function creates a new Patient object by calling the appropriate constructor. You should validate the given patient’s data before creating a new object. You should not create a new object if pSSN matches an existing patient’s SSN; just print an error message. Otherwise, you should create an object and add it to the patientsRecords vector and display a message that the patient object was successfully added.

Note that patientCheckups vector is initially empty. It is updated in addPatientCheckup method.




<ul>

 <li><em>void HealthRecords::printAllPatients(); </em></li>

</ul>




This function prints basic information about all patients in the patientsRecords vector. For each patient, you should print the following information: patient’s account number, first name, last name, gender, date of birth. If there are no patients, you should print an appropriate error message.

<em> </em>

<ul>

 <li><em>void HealthRecords::addPatientCheckup (long pNum, string cDate, double pHeight, double pWeight, double pCholesterol, double pHDL, double pTriglyceride, double pGlucose, double pBloodPressure); </em></li>

</ul>




This function creates a Checkup object and adds it to the patient’s list of checkups, that is, to the vector of patientCheckups for the patient account whose number is pNum. You need to ensure that patient account number is valid before adding the checkup to the patientCheckups vector. You should also display a message that the checkup entry is successfully added. Otherwise, you should not add any object to the vector and should print appropriate error messages.







<ul>

 <li><em>void HealthRecords::printPatientCheckupSummary(long pNum, string sDate); </em></li>

</ul>




This function prints a detailed individual checkup report from a patient’s profile. You should first search for the patient whose account number is pNum and specifically for the checkup held on sDate. If no such entry is found, you should print an appropriate message. If an entry is found, you should print a detailed summary of that checkup along with medical warnings to the patient. This includes displaying personal information, test results and final notes to patient.




Personal information includes the patient’s name, age in years <u>(calculated)</u>, gender, and date of birth.




Test results include some measured metrics and calculated metrics. Measured ones are total Cholesterol, HDL cholesterol, triglycerides, Glucose, and blood pressure, Calculated test results are LDL cholesterol level, total cholesterol to HDL cholesterol ratio, and Body Mass Index (BMI). These may be obtained as follows:




<ul>

 <li>LDL cholesterol level <u>(calculated)</u> is obtained by dividing triglyceride concentrations by 5, subtracting it and the HDL cholesterol from the total cholesterol level.</li>

</ul>




<ul>

 <li>Cholesterol/HDL ratio <u>(calculated)</u> is obtained by dividing the total cholesterol level by the HDL cholesterol level.</li>

</ul>




<ul>

 <li>Body Mass Index <u>(calculated)</u> is obtained by multiplying the weight in pounds by 703, then dividing by height in inches squared.</li>

</ul>




<strong>Note:</strong> you need to write member functions in the Checkup class to calculate each one of these <u>(calculated)</u> metrics.




Final notes to the patient summarize potential risks if any. Normal reference ranges of each metric are shown below:




<em>—————————————————————- </em>

<em>Total Cholesterol (Reference Range: 125-199mg/dL) </em>

<em>HDL Cholesterol (Reference Range: &gt; or = 40 mg/dL) </em>

<em>Triglycerides (Reference Range: &lt; 150 mg/dL) </em>

<em>LDL Cholesterol (Reference Range: &lt; 130 mg/dL ) </em>

<em>Cholesterol/HDL Ratio (Reference Range: &lt; or = 5.0) </em>

<em>Glucose (Reference Range: 65-99 mg/dL) </em>

<em>Blood Pressure (Reference Range: &lt; 120/80 mmHg)</em>

<em>Body Mass Index (Reference Range: 18.5-24.9) </em>

<em>————————————————————— </em>




The first six results are indicators of the heart health and heart disease risks. Results falling outside reference ranges are associated with “a high risk of coronary heart disease”.




A normal value for Blood Pressure is &lt; 120/80mmHg. If either the top number or the bottom number is above the specified range, the patient may have “hypertension”.




The BMI is an indication of body total fat. Target values are between 18.5 and 24.9. A BMI of 25 or above is linked to an “overweight with increased risk for health conditions such as heart disease, stroke…” . A BMI of less than 18.5 is considered “underweight with increased risk of electrolyte imbalances and osteoporosis”.







For example,




printPatientCheckupSummary 5004 10/22/2016…







<em>Amelia Perez  </em>

<em>Born on 12/05/1983, Female </em>

<em>32 years old, 5’1”, 157 pounds </em>

<em> </em>

<em> </em>

<em>                                    10/22/2016 </em>

<em>—————————————————————- </em>

<em>Total Cholesterol                   210  </em>

<em>(Reference Range: 125-199mg/dL) </em>

<em> </em>

<em>HDL Cholesterol                     68  </em>

<em>(Reference Range: &gt; or = 40 mg/dL) </em>

<em> </em>

<em>Triglycerides                       135          </em>

<em>(Reference Range: &lt; 150 mg/dL) </em>

<em> </em>

<em>LDL Cholesterol                     115  </em>

<em>(Reference Range: &lt; 130 mg/dL) </em>

<em> </em>

<em>Cholesterol/HDL Ratio              3.09   </em>

<em>(Reference Range: &lt; or = 5.0) </em>

<em> </em>

<em>Glucose                             84                       </em>

<em>(Reference Range: 65-99 mg/dL) </em>

<em> </em>

<em>Blood Pressure                      99/50  </em>

<em>(Reference Range: &lt; 120/80 mmHg) </em>

<em> </em>

<em>Body Mass Index                     29.47  </em>

<em>(Reference Range: 18.5-24.9) </em>

<em> </em>

<em>————————————————————— </em>Notes to patient:

– <em>Is Overweight </em>with increased risk for health conditions such as heart disease, stroke…

—————————————————————

<em> </em>

<em> </em>

&#x25aa; <em>void HealthRecords::printPatientHistory(long pNum); </em>




This function prints the medical history of a specific patient whose patient account number is pNum. This includes printing a patient’s general information followed by a medical summary report. General information includes the patient’s first name, last name, gender, and date of birth. The medical report includes a table summarizing all the patient’s test results. For example:




<em>Amelia Perez  </em>

<em>Born on 12/05/1983, Female </em>

<em> </em>

<em>                                    10/2015     10/2016     10/2017 </em>

<em>——————————————————————— </em>

<em>Total Cholesterol                   188         210         182 </em>

<em>(Reference Range: 125-199mg/dL) </em>

<em> </em>

<em>HDL Cholesterol                     58          68          48 </em>

<em>(Reference Range: &gt; or = 40 mg/dL) </em>

<em> </em>

<em>Triglycerides                       58          135         70 </em>

<em>(Reference Range: &lt; 150 mg/dL) </em>

<em> </em>

<em>LDL Cholesterol                     118         115         120 </em>

<em>(Reference Range: &lt; 130 mg/dL) </em>

<em> </em>

<em>Cholesterol/HDL Ratio              3.24        3.09        3.79  </em>

<em>(Reference Range: &lt; or = 5.0) </em>

<em> </em>

<em>Glucose                             89          84          88  </em>

<em>(Reference Range: 65-99 mg/dL) </em>

<em> </em>

<em>Blood Pressure                      99/53       99/50       99/56 </em>

<em>(Reference Range: &lt; 120/80 mmHg) </em>

<em> </em>

<em>Body Mass Index                     28.15       29.47       31.53 </em>

<em>(Reference Range: 18.5-24.9)  </em>

<em>——————————————————————— </em>

<em> </em>




&#x25aa; <em>void HealthRecords::processTransactionFile(string fileName); </em>




This function opens the transaction file and processes its lines one by one. If the file could not be opened, you should print appropriate error message.




Note: Any member function that does not modify the attributes must be made constant.




After you design your classes (make sure to break up your classes into .cpp and .h files), write a main program that instantiates an object of type <em>HealthRecords</em> and calls a method to read a transaction file and process its commands. Your main should look like this:




int main()

{

HealthRecords  hr;

hr.processTransactionFile(“HW2.txt”);




return 0;

}




The transaction file contains several commands and corresponding values. The commands and their formats are:

<ul>

 <li>CreateNewPatient  fName            lName  pSSN pGender pBirthDate</li>

</ul>




<ul>

 <li>AddPatientCheckup pNum cDate pHeight pWeight pCholesterol pHDL pTriglyceride pGlucose pBloodPressure</li>

</ul>




<ul>

 <li>PrintAllPatients</li>

</ul>




<ul>

 <li>PrintPatientCheckupSummary pNum cDate</li>

</ul>




<ul>

 <li>PrintPatientHistory pNum</li>

</ul>




<ul>

 <li>ProcessTransactionFile fileName</li>

</ul>




A sample transaction file is shown below. You may use it to test your code:

CreateNewPatient Joe Garcia 432345673 M 11/10/1979

CreateNewPatient Suzy Walter 876523067 F 01/01/2010

CreateNewPatient Amelia Perez 876007654 F 12/05/1983

CreateNewPatient Tim Ducrest 123282345 M 01/12/2000

CreateNewPatient Amelia Perez 876007654 F 12/05/1983

CreateNewPatient Suzy Walter 987667654 F 09/20/1965




PrintAllPatients




AddPatientCheckup 5000 10/10/2015 5.8 210 160 33 178 88 123/78

AddPatientCheckup 5000 09/29/2016 5.8 215 165 29 312 91 129/86

AddPatientCheckup 5002 11/06/2016 4.1 70 180 69 120 80 101/78

AddPatientCheckup 5002 04/10/2017 4.2 75 198 65 120 81 100/76

AddPatientCheckup 5004 11/10/2015 5.1 150 188 58 58 89 99/53

AddPatientCheckup 5004 10/22/2016 5.1 157 210 68 135 84 99/50

AddPatientCheckup 5004 11/06/2017 5.1 168 182 48 70 88 99/56

AddPatientCheckup 5005 05/11/2017 5.2 165 180 49 70 88 100/56

AddPatientCheckup 5006 02/04/2017 5.9 170 202 36 301 90 126/87 AddPatientCheckup 5008 08/18/2017 5.4 180 165 42 200 105 105/76




PrintPatientHistory 5000

PrintPatientHistory 5002

PrintPatientHistory 5004

PrintPatientHistory 5006

PrintPatientHistory 5008

PrintPatientHistory 5010




PrintPatientCheckupSummary 5000 09/29/2016

PrintPatientCheckupSummary 5002 11/06/2016

PrintPatientCheckupSummary 5002 09/29/2017

PrintPatientCheckupSummary 5004 10/22/2016

PrintPatientCheckupSummary 5008 08/18/2017


