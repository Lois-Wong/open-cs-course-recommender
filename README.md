To use our code, please navigate to https://colab.research.google.com/drive/1VeXooAxDorZ6R0bOaXWzJmegizkPPWwI?usp=sharing

How to Use our Code

Users who wish to navigate the open-source CS course landscape can run course_ rec.ipynb on Colab or Jupyter in order to engage with the database we have created. This notebook allows for three main functionalities: (1) viewing all listings in our database, (2) searching the database via string input, and (3) entering a description of one's CS goals. Each functionality occurs by running one or more code blocks grouped by functionality heading ("Public Access Computer Science Course Database", "Search the database", and "Finding courses that suit your goals").

Functionality (1) allows the user to view all courses in the database, ten courses at a time. For each course, the title, description, link, and source (either MIT OpenCourseware or Coursera) is displayed. After viewing ten courses, the user can expand the output in order to view ten more courses.

Functionality (2) allows the user to enter a token. After the token is entered, our program will search the title and description of each course for the appearance of that token. Courses containing the token in their titles or descriptions will be outputted, ten courses at a time. If the token does not appear in any course title or description, our program will output "No Matches."

Functionality (3) allows the user to enter a description of their learning goals for their CS education. After they enter this description, the course descriptions that have the highest cosine similarity score to the user-entered description will be outputted in ranked order.
