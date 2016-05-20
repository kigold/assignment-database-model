#Database Model for a Laundry Service Application

###Database Model Diagram
![alt text](https://github.com/kigold/assignment-database-model/blob/development/db_model.png "Logo Title Text 1")

###Introduction
#####This is a model of the customer interaction of a laundry service application, this model makes provision for all the basic data requirement of customer object with the laundry service application. Activities such as:-
#####..*customer details
#####..*customer tasks
#####..*list of items in each tasks, etc
#####The idea is that the customer table is linked to the task table, for every task  created for a user, a column is generated on the task table and it is tied to customer table via the customer_id foreign key, 
#####The task table does not provide all the details of the task, it only has general details for the task, more specific details are found in the task_list table which is linked in a similar manner, via foreign key [task_id and task_customer_id], this task_list grants us the flexibility of listing multiple items under one task_id.

###Queries
#####Basic queries that can be done on the table




