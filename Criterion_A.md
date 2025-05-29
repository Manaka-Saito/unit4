# Criterion A

## Problem Definition

   My client, A.S., is a Japanese high school student frustrated with the current meal providing system. Specifically, the school serves three meals a day with 3 options in each meal: main course, noodles stall and special menu. The students receive notification about the menu of each day via email. However, A.S finds reading the emails inconvenient during the days as it got mixed up with her other school-related emails and the format is also not quite user-friendly – instead of displaying the all available options, the current menu only showcases the main course, which is sometimes inaccurate. 

   Secondly, the school is also known for having a lengthy queue during mealtimes due to the new salad bar area implemented. Hence, it becomes impossible for A.S to estimate her waiting time unless she goes to the cafeteria and waits, which poses a challenge of productivity that she wants to resolve.  

   Last but not least, she emphasizes that the current system doesn’t ask for student’s input and preference in terms of food selection. Therefore, not only does the cafeteria not have a comprehensive perspective on what sort of food students currently prefer, but it also raises a challenge of an excessive amount of leftovers. Although the cafeteria staff logs leftovers quantities daily, the process is manual, hence error-prone, and data is not easily accessible for. Furthermore, the data is recorded in tables that are not easily interpreted. Altogether, these challenges underscores the need for a more interactive and comprehensive solution to enhance the dining experience at A.S’s school.

[See Appendix A for client consultation proof.](IA_Appendix)



## Proposed Solution

   Considering the client’s needs that all students have access to the system and be able to see the updates immediately, an adequate solution would be a web-based system developed with Python, Flask, and an SQLite database.  

   Web-based system is the optimal choice as users can interact from any device without requiring users to install software. Since the client and end users will be whole students plus faculty and cafeteria workers, they use different devices such as smartphones and laptops, and therefore it is best to make it a web-based system rather than a desktop application for better compatibility. While there is an option of desktop or mobile apps, web-based is more accessible and updates are centralized which means that all users can see the latest data.[^1] I proposed to use Python to create the web application because in comparison to other popular languages such as Java, it is supported by major operating systems. This is suitable for the clients who want access to the system from any devices that students, faculty or cafeteria workers have. Additionally, Python is an open-source which means that no license is required to purchase. Considering that the client is a student who has a limited amount of money she can pay for the system, Python is suitable for tackling issues. [^2]

   For frameworks, I proposed to use Flask. Unlike other frameworks popular for web applications such as Django, Flask is especially easy to incorporate additional functionalities without rebuilding the entire application.[^3] This allows the system to be expanded more easily when clients want it to be. Moreover, it is efficient and runs smoothly on limited resources such as school-provided laptops. This is an advantage when the end-users are the whole school because some people have limited resources. [^4]

   Lastly, I proposed to use SQLite for databases. SQLite is free to use for everyone unlike MySQL or MongoDB. This allows clients to allocate money on different factors or save it especially when the client is a high school student. [^5]

## Success Criteria 

### Admin
1. The solution allows the cafeteria workers to receive email notifications of the summary of the week including the statistics of the amount of food waste and attendance rate, and feedbacks from students.
   
    -> ```** [Issue solved**: “Therefore, not only does the cafeteria not have a comprehensive perspective on what sort of food students currently prefer, but it also raises a challenge of an excessive amount of leftovers. Although the cafeteria staff logs leftovers quantities daily, the process is manual, hence error-prone, and data is not easily accessible for.”]```  

2. The solution allows the cafeteria workers to see the visualized statistics of the attendance, student preferences for each dish, and amount of food waste.
   
    -> ```**[Issue solved**: "Although the cafeteria staff logs leftovers quantities daily, the process is manual, hence error-prone, and data is not easily accessible for. Furthermore, the data is recorded in tables that are not easily interpreted." ]```  

3. The solution allows the cafeteria workers to upload photos and names of today's dishes.
   
    -> ```**[Issue solved**: “instead of displaying the all available options, the current menu only showcases the main course, which is sometimes inaccurate.” ]```  
 
### Student
4. The solution provides a feedback and rating system for the dish.  

    -> ```**[Issue solved**: “she emphasizes that the current system doesn’t ask for student’s input and preference in terms of food selection” ]```  
 
5. The solution displays today’s  meals with explanations.  

    -> ```**[Issue solved**: “instead of displaying the all available options, the current menu only showcases the main course” ]```  
 
6. The system lets students indicate if they plan to attend each meal.  

    ->```**[Issue solved**: “these challenges underscores the need for a more interactive and comprehensive solution to enhance the dining experience at A.S’s school” ]```  
 
7. The solution displays how long the queue is and estimation of the waiting time.  

    ->```**[Issue solved**: “Hence, it becomes impossible for A.S to estimate her waiting time unless she goes to the cafeteria and waits”  ]```  
 
### For Everyone

8. Sign in/Log in Systems to distinguish between students and faculty, and cafeteria workers.

    -> ```**[Issue solved**: “current system doesn’t ask for student’s input and preference in terms of food selection” ]```

[^1]: Desai, J. (2023, December 27). Web application vs Desktop Application: Pros and cons. Positiwise. https://positiwise.com/blog/web-application-vs-desktop-application-pros-and-cons#Cross-Platform_Compatibility
[^2]: says:, A. S. (2025a, February 22). 5 ways python web development cuts costs and boosts business efficiency. Read Our Blog – Webguru Infosystems Latest updates on website development, mobile app development and digital marketing. https://www.webguru-india.com/blog/5-ways-python-web-development-cuts-costs-and-boosts-business-efficiency/
[^3]: Django vs Flask: The best python web framework in 2024?. The Official Cloudways Blog. (2025, March 11). https://www.cloudways.com/blog/django-or-flask/ 
[^4]: Bahgat, A. (2023, December 29). Flask vs Django: Let’s choose your next python framework. Kinsta®. https://kinsta.com/blog/flask-vs-django/
[^5]: Orel, A. (2024, August 15). Pros and cons: Mysql, PostgreSQL, sqlite, mongodb. Skynix LLC. https://skynix.co/resources/pros-and-cons-mysql-postgresql-sqlite-mongodb
