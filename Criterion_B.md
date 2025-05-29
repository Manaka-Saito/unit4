# Criterion B

## System Diagram

<img width="1000" alt="Screenshot 2025-05-29 at 9 41 52" src="https://github.com/user-attachments/assets/2e0786cf-bd35-4bea-8a3c-a3d5efce834b" />
Fig 1. *System Diagram of proposed solution*

## ER Diagram
<img width="1000" alt="Screenshot 2025-05-29 at 11 35 26" src="https://github.com/user-attachments/assets/7d5184a4-0a92-4638-95d4-3c3482590d90" />

Fig 2. *ER Diagram of Proposed Solution*

## Database Picture
1. `user ` Table
<img width="1000" alt="Screenshot 2025-05-29 at 10 11 36" src="https://github.com/user-attachments/assets/632e725a-caca-42b8-824c-309603f1c784" />
Fig 3. *Database of `user`*

2. `feedback` Table
<img width="1000" alt="Screenshot 2025-05-29 at 10 22 51" src="https://github.com/user-attachments/assets/58a2797f-e5b3-4b72-b1a9-56c554f1e0e5" />
Fig 4. *Database of `feedback`*


3. `dish` Table
<img width="1000" alt="Screenshot 2025-05-29 at 10 57 18" src="https://github.com/user-attachments/assets/dc5cb107-a638-485e-a500-68812c608545" />
Fig 5. *Database of `dish`*

4. `daily_menu` Table
<img width="1000" alt="Screenshot 2025-05-29 at 11 42 04" src="https://github.com/user-attachments/assets/dca03b08-f2c2-404a-95c5-702526f801e8" />
Fig 6. *Database of `daily_menu`*

5. `attendance` Table
<img width="1000" alt="Screenshot 2025-05-29 at 11 26 52" src="https://github.com/user-attachments/assets/d68ca269-5b02-4a73-8af2-a877a7b4c91d" />
Fig 7. *Database of `attendance`*

6. `food_waste` Table
<img width="1000" alt="Screenshot 2025-05-29 at 11 39 04" src="https://github.com/user-attachments/assets/71d15614-96bc-4877-a4ce-cdc4248fdd95" />
Fig 8. *Database of `food_waste`*

## Flow Diagrams

<img width="1000" alt="Screenshot 2025-05-29 at 13 40 06" src="https://github.com/user-attachments/assets/5a813a36-1d7a-4844-bc54-f0f878b81d0f" />  

Fig 9. *Flow chart of `post_menu` function*  

<img width="1000" alt="Screenshot 2025-05-29 at 17 18 42" src="https://github.com/user-attachments/assets/0affbe57-2609-4f99-8b6d-4509e55e9550" />  

Fig 10. *Flow chart of `get_dishes` function*  






## Record of Tasks
| Task Number 	| Task                                	| Planned Outcome                                                                                                                                                                                                                                                                                                    	| Time Estimated(Min) 	| Target Completion Date 	| Criterion 	|
|-------------	|-------------------------------------	|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|---------------------	|------------------------	|-----------	|
| 1.          	| Meet with my client                 	| Consult with my client to have a clear understanding of situation and their needs.                                                                                                                                                                                                                                 	| 20                  	| April 20               	| A         	|
| 2.          	| Define a problem definition         	| Write a problem definition to clarify the situation and problems that needs to be solved.                                                                                                                                                                                                                          	| 20                  	| April 22               	| A         	|
| 3.          	| Write and propose success criteria  	| List all success criteria that needs to meet in final product, and review them wiht client, getting consensus on all of them.                                                                                                                                                                                      	| 40                  	| April 23               	| A         	|
| 4.          	| Justification of Tools              	| Do research on development tools to determine the most adequate tools to use for this project.                                                                                                                                                                                                                     	| 30                  	| April 24               	| B         	|
| 5.          	| Create ER diagram                   	| Create the ED diagram to organize relationships identifying attributes and figure out the data needed.                                                                                                                                                                                                             	| 40                  	| April 24               	| B         	|
| 6.          	| Create UML diagram                  	| Create the UML diagram to understand the use of classes and variables need to structuer the whole product.                                                                                                                                                                                                         	| 60                  	| April 25               	| B         	|
| 7.          	| Create a system diagram             	| Construct the sysmtem diagram to visualize the structure and deployment of the final application.                                                                                                                                                                                                                  	| 40                  	| April 27               	| B         	|
| 8.          	| Design the wireframe of the program 	| Develop an overview of the final product to get grasp of what needs to get done                                                                                                                                                                                                                                    	| 40                  	| April 29               	| B         	|
| 9.          	| Set up database                     	| Create database, and create all data tables (user, food_waste, feedback, dish, dish_menu, attendance) to store data inputted and to interact to support core applciation functions.                                                                                                                                	| 80                  	| May 1                  	| C         	|
| 10.         	| Signup Page                         	| Create a sign up screen and a database and functions that stores unique id, username, email, and password. Insert the information that gets input into the screen into the database. Using the function, hash the password to protect information. Also, create additional columns to fill only for admin signup.  	| 80                  	| May 1                  	| C         	|
| 11.         	| Login Page                          	| Create a login functions and allow users to login by inputting the correct username and password.                                                                                                                                                                                                                  	| 80                  	| May 2                  	| C         	|
| 12.         	| Customer Page                       	| Create a main page for students that displays the navigation bar at the top to direct to Menu page, Feedback page, Estimated Waiting Time page and Logout                                                                                                                                                          	| 60                  	| May 15                 	| C         	|
| 13.         	| Admin Page                          	| Create a main page for admin that displays the navigation bar at the top to direct to Post Menu page, Statics page and Logout                                                                                                                                                                                      	| 60                  	| May 16                 	| C         	|
| 14.         	| Posting menu Page                   	| Create a posting menu page where only admin can have access to. Allows users to input dish name and date with availability of sorting by category and meal time which will be stored in a data table.                                                                                                              	| 120                 	| May 18                 	| C         	|
| 15.         	| Create new dish Page                	| Create a create new dish page where only admin have access to. Create a form that requires input of dish name, category, meal time, picture and any comments. Data will be stored in a user database after the validation of inputs such as image type.                                                            	| 150                 	| May 19                 	| C         	|
| 16.         	| Menu Page                           	| Create a menu page that students have access to. Displays today's dish details, name, category, meal time and image, retrieving dish name, category and image link. Allows users to input whether they are attending to the meal, inserting them into the data table.                                              	| 100                 	| May 21                 	| C         	|
| 17.         	| Feedback Page                       	| Create a feedback page that students have access to. Create a form that requires input of feedback message and optional input of dish. Functionality that insert input and date of input into database are created.                                                                                                	| 70                  	| May 24                 	| C         	|
| 18.         	| Static Page                         	| Create a static page that admin have access to. Displays a visualized line graph of attendance rate and food waste amount. Display dishes served on the day when usrs to hover over for each points in a graph.                                                                                                    	| 200                 	| May 28                 	| C         	|       	|

## Test Plan
