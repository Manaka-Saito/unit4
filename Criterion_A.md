# Criterion A

## Problem Definition

	My client, A.S., is a Japanese high school student frustrated with the current meal providing system. Specifically, the school serves three meals a day with 3 options in each meal: main course, noodles stall and special menu. The students receive notification about the menu of each day via email. However, A.S finds reading the emails inconvenient during the days as it got mixed up with her other school-related emails and the format is also not quite user-friendly – instead of displaying the all available options, the current menu only showcases the main course. 
Secondly, the school is also known for having a lengthy queue during mealtimes due to the new salad bar area implemented. Hence, it becomes impossible for A.S to estimate her waiting time unless she goes to the cafeteria and waits, which poses a challenge of productivity that she wants to resolve. 
Last but not least, she emphasizes that the current system doesn’t ask for student’s input and preference in terms of food selection. Therefore, not only does the cafeteria not have a comprehensive perspective on what sort of food students currently prefer, but it also raises a challenge of an excessive amount of leftovers. Altogether, these challenges underscores the need for a more interactive and comprehensive solution to enhance the dining experience at A.S’s school.

See Appendix A for client consultation proof.


## Proposed Solution
	Considering the client’s needs that all students have access to the system and be able to see the updates immediately, an adequate solution would be a web-based system developed with Python, Flask, and an SQLite database. 

Web-based system is the optimal choice as users can interact from any device without requiring users to install software. Since the client and end users will be whole students plus faculty and cafeteria workers, they use different devices such as smartphones and laptops, and therefore it is best to make it a web-based system rather than a desktop application for better compatibility. While there is an option of desktop or mobile apps, web-based is more accessible and updates are centralized which means that all users can see the latest data. I proposed to use Python to create the web application because in comparison to other popular languages such as Java, it is supported by major operating systems. This is suitable for the clients who want access to the system from any devices that students, faculty or cafeteria workers have. Additionally, Python is an open-source which means that no license is required to purchase. Considering that the client is a student who has a limited amount of money she can pay for the system, Python is suitable for tackling issues. 

For frameworks, I proposed to use Flask. Unlike other frameworks popular for web applications such as Django, Flask is especially easy to incorporate additional functionalities without rebuilding the entire application . This allows the system to be expanded more easily when clients want it to be. Moreover, it is efficient and runs smoothly on limited resources such as school-provided laptops. This is an advantage when the end-users are the whole school because some people have limited resources. 

Lastly, I proposed to use SQLite for databases. SQLite is free to use for everyone unlike MySQL or MongoDB. This allows clients to allocate money on different factors or save it especially when the client is a high school student.

## Success Criteria 

Admin
The solution allows the cafeteria workers to receive email notifications of the summary of the week including the statistics of the amount of food waste and comments from students.
 -> [Issue solved: “these challenges underscores the need for a more interactive and comprehensive solution to enhance the dining experience at A.S’s school”  ]

The solution allows the cafeteria workers to see the statistics of the attendance, student preferences for each dish, and amount of food waste.
 -> [Issue solved: “these challenges underscores the need for a more interactive and comprehensive solution to enhance the dining experience at A.S’s school” ]

The solution allows the cafeteria workers to upload photos and names of today's dishes.
 -> [Issue solved: “instead of displaying the all available options, the current menu only showcases the main course” ]
Student
The solution provides a feedback and rating system for the dish. 
 -> [Issue solved: “she emphasizes that the current system doesn’t ask for student’s input and preference in terms of food selection” ]
The solution displays today’s  meals with explanations.
 -> [Issue solved: “instead of displaying the all available options, the current menu only showcases the main course” ]
The system lets students indicate if they plan to attend each meal.
 -> [Issue solved: “these challenges underscores the need for a more interactive and comprehensive solution to enhance the dining experience at A.S’s school” ]
The solution displays how long the queue is and estimation of the waiting time.
 -> [Issue solved: “Hence, it becomes impossible for A.S to estimate her waiting time unless she goes to the cafeteria and waits”  ]
For Everyone

Sign in/Log in Systems to distinguish between students and faculty, and cafeteria workers.
 -> [Issue solved: “current system doesn’t ask for student’s input and preference in terms of food selection” ]
