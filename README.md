# Salesforce_CarRenting_Project
This project is build using Salesforce. The main motive of this project is to build an application in salesforce where users can submit their car for rent and also book a car for rent.

The Structure of the project:

1. An object for car's available must be created where all the cars available for rent and the submitted cars by the users must be stored in the form of records.
2. An object for bookings must be created where it acts as a child object for car's available object
3. An object to store the details of all car owners which acts as a parent object to car's available object.
4. An customers object to store the details of all the customers who booked the car using the application.

Fields of car owner object:
1. Owner Name
2. Owner Email
3. Owner mobile number

Fields of car's available object:
1. Car Id: auto generated.
2. Car Maker (pick list value)
3. Car Model (pick list value) the above and this field will be dependent fields.
4. Car reg no: (must be unique value to avoid creating muliple records of same car by the car owner).
5. Car chassis no: (must be unique value to avoid creating muliple records of same car by the car owner).
6. Car available up to (set a date field)
7. Disable for now checkbox. (if it is true/active then the car will not be displayed in the rent car list).

Fields of customers object:
1. Booking Id(auto generated)
2. Customer Name
3. Customer Email
4. Car booked
5. Booked date

Logics and Validations:
There will be two buttons available on the home page
1. Put your car/ Activate your car.
2. Remove your car/ Disable your car.
3. Get a car.
4. Submit the car.

By clicking on "Put your car/ Activate your car" user must be able to submit his car for others for renting purposes.
-User have two options to select, one is to activate car, the other one is to enter a car.
-By clicking the first option user will be asked to fill the car registration number and chassis number fields of car's available object and the email field from the owners object.
-The email field will be validated if the owner record exists or not, if exists the related records will be retrieved and the remianing details will be validated and if any records matches from the retrieved records, that record will be displayed with a button called activate. If not the error message " No user found with this email address".
-When the user click on activate button the "Disable for now checkbox" must unselect so that the car can be displayed in the rent list.
-If the user selects put your car option then user will enter all the fields available in car's availale object and car owner's object.
-As soon as the details are entered, the data from the fields of car owners object will be validated. 
-If the email of the owner already exixts in the owner's object the entry will be ignored in the owners object and a record will be created in the car's available object.
-If the email of the owner does not exist in the owner's object then a record will be created in the owner's module and then a record will be created in the car's available object.


By clicking on "Remove your car" user must be able to remove his car from the car's rent list.
-User must select a value from 2 values, one is remove car temporarily, the other one is remove car permanently.
-When a user selects the first option the "Disable for now" he need to provide car reg number and the chassis no, the matching record will be selected and it's checkbox "Diable for now" must be true/active in the car's available object.
-When a user selects the second option, he need to provide car reg number and the chassis no, the matching record will be selected and deleted from the object permanently.
