# Criterion C

## Techniques Used:  

- If/Else statements
- For loops
- Endpoints, HTTP methods such as GET, POST
- Database
- Password Hashing
- Input validation
- File Upload and Output 
- DatabaseManager
- Frontend and backend interaction
- Data Filtering
- Graphing data 
- Dictionary

## Existing Tools Used (Libraries and Modules)
- Jinja
- Flask
- os
- datetime
- SQLite
- werkzeug.utils (secure_filename())

### References

### [Codehal](https://www.youtube.com/@codehal)
Codehal is a youtube channel that explains the basic HTML and CSS skills.

### [ionicons](https://ionic.io/ionicons/usage)
ionicons is a open source of icons that can be used in HTML and CSS.

### [W3Schools](https://www.w3schools.com/css/)
W3Schools provides basic information and sample code of html, css, and javascript with preview.

### [Bootstrap](https://getbootstrap.jp/docs/4.1/components/buttons/)
Bootstrap provides front-end framework that allows the visual to be consistent.

### [freeCodeCamp](https://www.youtube.com/@freecodecamp)
freeCodeCamp is a youtube channel that provides tutorials for openCV, especially how to detect human's body. 

### **1. Posting Menu with Data Filtering**  

  As per success criteria 3, the website needs to have a menu posting system to improve accuracy of daily dishes communicated with students. To address this, I decided to develop functions, *post_menu*, supported by supplemental functions,*get_dishes* and *updateDishOptions*, and two data tables, *dish* and *daily_menu* to allow admin users to post daily menus.  

**Database**
Firstly, suitable tables in a database to store daily dish information are created. They are created with the following SQL command.

```.py
dish = """CREATE TABLE if not exists dish(
   id INTEGER PRIMARY KEY AUTOINCREMENT,
   name TEXT NOT NULL,
   meal_time TEXT,
   category TEXT,
   picture TEXT,
   comment TEXT
)"""


daily_menu = """CREATE TABLE if not exists daily_menu(
   id INTEGER PRIMARY KEY,
   dish_id INTEGER NOT NULL,
   date DATE NOT NULL,
   FOREIGN KEY (dish_id) REFERENCES dish(id) ON DELETE CASCADE ON UPDATE CASCADE
)"""
```  

The command *dish* creates a table called *dish* with the columns *id*, *name*, *meal_time*, *category*, *picture* and *comment*. *id* is an integer primary key that automatically increments. The table requires to have *name* as without it, it cannot accomplish its role in functions.  

Another command *daily_menu* creates a table called *daily_menu* with the columns *id*, *dish_id* and *date*. *dish_id* is a foreign key retrieved from a table *dish* to ensure the integrity between two tables and prevent invalid or erroneous data from being entered.  Additionally, it is set to modify accordingly when *dish(id)* is modified. This ensures maintainability and accuracy of data stored in *daily_dish*.  

Initially, there was only *daily_menu* table with the columns that *dish* has. However, since it requires admin users to input all details every time they post a menu for a day, there is a lot of redundancy and inefficiency. Moreover, the table was not the easiest table to handle since it quickly became lengthy with relatively many columns. For better user experience and maintainability, I decided to create two separate tables, and relating it from one table to another, *daily_menu* to *dish*.
 
**Conditional Statement/datetime/HTTP Methods**
I developed a function *post_menu* to achieve a dynamic menu posting system and lessen manual errors.  

```.py
@app.route('/admin/menu', methods=['GET', 'POST'])
def post_menu():
   db = DatabaseManager('my_caf.db')
   query = "SELECT id, name FROM dish"
   all_dish = db.search(query, [])
   db.close()
   today = datetime.today().isoformat()


   if request.method == 'POST':
       dish_id = request.form.get('dish_id') #getting the id of dish
       date = request.form.get('menu_date')  
	 #if inputs are completed, insert data into a data table,
	 #if not, then display error message
       if dish_id and date:
	     
           query = "INSERT INTO daily_menu(dish_id, date) VALUES (?,?)"
           db.run_save(query, (dish_id, date,))
           db.close()
           flash("Dish added correctly!!", 'success')
           return redirect(url_for('post_menu'))


       else:
           flash("Please fill in all required fields", 'error')
           return redirect(url_for('post_menu'))


   return render_template('IA_template/admin_menu.html', today_date = today, all_dish = all_dish)
```
*Fig. 1 *post_menu* Function

This code defines a *post_menu* function that is linked with the URL path of */admin/menu* handling *GET* and *POST* HTTP methods. First, it initializes the connection to the database *my_caf.db* and declare *query* which SQLite query that retrieves *id* and *name* from data table *dish*, and execute and store the result in a variable *all_dish*. Same as this, before the conditional statement , a variable named *today* stores today’s date using imported library **datetime**. Both *all_dish* and *today_date* are passed to HTML template, *’IA_template/admin_menu.html’* for predefined options for dish name dropdown in frontend, and pre-fill the date input field in the admin form. Pre-filled date input field to today ensures user-friendliness because it allows admin users to find the date more easily and less incorrectly compared to when they have to input date manually. 

When a *POST* request is received, it retrieves the HTML form input, *dish_id* and *menu_date*. If they are not empty, these values are inserted into the database *daily_dish*, displaying the success message and redirecting to the page clearing the form to prevent double submission. If required form inputs aren’t filled, an error message is displayed. This conditional statement is used for validation of input to prevent incomplete data to be stored that possibly triggers the server to crash. It ensures data reliability and system stability. 

**Data Filtering/Dictionary**  
While *post_menu* functions to render template and insert data into a data table or display error otherwise, I developed *get_dishes* function, a function that is triggered when *fetch()* is called from JavaScript,  to clinch usability in future and keep human error less system. *get_dishes* collaborate with JavaScript to filter and specify dish name options in dropdown based on user's selection in *meal_time* and/or *category*. 

```.py
@app.route('/get_dishes')
def get_dishes():


   #retrieve each data from URL
   time = request.args.get('time')
   dish_type = request.args.get('type')


   db = DatabaseManager('my_caf.db')
   query = "SELECT id, name FROM dish"


   conditions = [] #parameters to add to query for filtering


   if time:
       query +=" WHERE meal_time = ?"
       conditions.append(time)


   if dish_type:
       if len(conditions) != 0:
           query += " AND category = ?"
       else:
           query += " WHERE category = ?"
       conditions.append(dish_type)


   dishes = db.search(query, conditions)
   db.close()


   #tuple for id and dish name
   dish_data = [{'id': d[0], 'name': d[1]} for d in dishes]
   return jsonify(dish_data)
```
Firstly, it retrieves selected *time* and *type* from URL. Then, it initializes a connection with *my_caf.db*. A variable *query* holds a foundation of query, and *conditions* is a tuple that stores any filters.  

The SQL query is modified utilising conditional statements, allowing users to select either one of filters or both. With modified *query* and *conditions*, data in *dishes* are searched and stores retrieved data that fulfills conditions. By using a loop that iterate through *dishes*, it stores each element into a dictionary. A dictionary is *dish_data* with keys, *id* and *name* and stores corresponding data as items.  I chose a dictionary because the code readability is improved and rather than getting intended data using indexes which are easily counted wrong, it reduces risk of making mistakes when getting intended data using keys. 

Finally the function returns *dish_data* that is converted into JSON format to JavaScript.  
