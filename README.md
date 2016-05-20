#Database Model for a Laundry Service Application

###Database Model Diagram
![alt text](https://github.com/kigold/assignment-database-model/blob/development/db_model.png "Logo Title Text 1")

###Introduction
#####This is a model of the customer interaction with a laundry service application, this model makes provision for all the basic data requirement of the customer object with the laundry service application, data requirenents such as:-
#####..*customer details
#####..*customer tasks
#####..*list of items in each tasks, etc
#####The idea is that the customer table is linked to the task table, for every task  created for a user, a column is generated on the task table and it is tied to customer table via the customer_id foreign key, 
#####The task table does not provide all the details of the task, it only has general details for the task, more specific details are found in the task_list table which is linked in a similar manner, via foreign key [task_id and task_customer_id], this task_list grants us the flexibility of listing multiple items under one task_id.

###Queries
####Basic queries that can be done on the table
####Get all customers
```sql SELECT name, phone, email FROM customer;
```

####Get all customers from a particular address
```sql
SELECT name, phone, email, address FROM customer WHERE address = 'Lagos Street';
```

####Get all customers from a particular address and with same email
```sql
   SELECT name, phone, email, address FROM customer WHERE (address = 'Lagos' Street) AND (email = 'myemail@mail.com');
```

####Get all tasks names, item_qty, and cost and user details for a user_id 88
```sql
SELECT task.task_name, task.item_qty, task.cost FROM task INNER JOIN customer ON task.customer_id=customer.customer_id WHERE task.customer_id='88';
```

####Get all task of a customer of id 22, with the list ordered by the cost, that is arranged according to the cost
```sql
 SEELECT * FROM task INNER JOIN customer ON task.customer_id=customer.customer_id WHERE task.customer_id='22' ORDER BY task.total_cost;
```

####Get all the items of and a customer in item list
```sql SELECT * FROM task_list INNER JOIN task ON task.customer_is=task_list.customer_id ORDER BY task.customer_id;
```





