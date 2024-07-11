#### Problem Statement

 Navigating the changing landscape of Computer Science is more difficult than ever, for both newcomers to the field and seasoned professionals aiming to stay informed and up-to-date on trends. With a plethora of decentralized resources and generic guides to learning Artificial Intelligence or Machine Learning from scratch, finding the right course to suit your needs and help you carve out your niche in this field can be overwhelming.  

 As of now, self-learners are left to haphazardly browse the web and enroll in the first or most affordable course they find--a method that not only impedes their satisfaction, but also neglects to consider their unique backgrounds, interests and potential contributions to the field. We aim to solve this problem by developing a tool that aggregates resources from different open courseware sites and recommends courses to users based on a plain text prompt about what they want to learn. 

#### Data & Methods

##### Web Crawling for Data Collection

 To centralize and organize existing learning resources, this platform leverages web crawling to gather open-access Computer Science courses names and descriptions from MIT OpenCourseWare and Coursera. We consider web crawling the optimal approach for this task because it allows us to efficiently gather a wide range of up-to-date information from diverse sources, ensuring our database is comprehensive and current. Additionally, web crawling offers the advantage of automating the data collection process, saving valuable time and resources compared to manual entry methods. 

**Web Crawling Statement**

 We acknowledge the importance of good robot "citizenship" and are committed to ensuring that our web robot operates within the guidelines set by the websites we visit. Our web crawler adheres to the directives specified in the robots.txt files of the websites and complies with the restrictions and limitations imposed by the website administrators. We have limited the scope of our web crawling activities to only the segments of the web that are directly relevant to our research purposes. For this project, we access each course webpage from the results of the educational sites' course search filtered to "Computer Science" results and collect the course title and description. 

##### Course Recommendation 

  For the  task of recommending courses to users, we provide the user with two methods of searching through our course database. 

  The first option begins by prompting the user to enter a token, which could be a keyword or phrase of interest. Subsequently, it filters our database of courses to include only those whose title or description contains the user input. This approach differs from existing platforms like Coursera, which often suggest related courses when a keyword doesn't yield exact matches. In contrast, this search method only returns courses directly relevant to the user's query, thus preventing the user from sifting through potentially irrelevant results. By providing more precise recommendations, this method saves users valuable time and effort in finding the most suitable courses for their needs. 

  Our second method begins by prompting the user to input their goals and objectives for an online Computer Science course. We utilize HuggingFace's SentenceTransformer model, paraphrase-MiniLM-L6-v2, to compute sentence embeddings for both our scraped course descriptions and the user's stated goals. Finally, we compute the Cosine similarity between each course description in our database and the user prompt and return the courses that best match the query, sorted in descending 

#### How to Use our Code

To use our code, please navigate to https://colab.research.google.com/drive/1VeXooAxDorZ6R0bOaXWzJmegizkPPWwI?usp=sharing

Users who wish to navigate the open-source CS course landscape can run cs-course-recommender.ipynb on Colab or Jupyter in order to engage with the database we have created. This notebook allows for three main functionalities: (1) viewing all listings in our database, (2) searching the database via string input, and (3) entering a description of one's CS goals. Each functionality occurs by running one or more code blocks grouped by functionality heading ("Public Access Computer Science Course Database", "Search the database", and "Finding courses that suit your goals").

Functionality (1) allows the user to view all courses in the database, ten courses at a time. For each course, the title, description, link, and source (either MIT OpenCourseware or Coursera) is displayed. After viewing ten courses, the user can expand the output in order to view ten more courses.

Functionality (2) allows the user to enter a token. After the token is entered, our program will search the title and description of each course for the appearance of that token. Courses containing the token in their titles or descriptions will be outputted, ten courses at a time. If the token does not appear in any course title or description, our program will output "No Matches."

Functionality (3) allows the user to enter a description of their learning goals for their CS education. After they enter this description, the course descriptions that have the highest cosine similarity score to the user-entered description will be outputted in ranked order.

#### Discussion 

##### Achivements 

The strengths and achievements of our projects are enumerated below: 

    - Innovative Use of Plain Text Queries: Our project introduces a novel approach of allowing users to input plain text queries about what they want to learn by leveraging developing LLM technology, ultimately providing a more intuitive and flexible interface. 
    - User-Friendly Interface: Encoding prompts and course information using an LLM provides the option for users to write longer, more detailed queries. This enhances the user experience and encourages deeper engagement with the system and significantly contributes to the usability and effectiveness of the tool.
    - Centralizing Open Courseware: By scraping and aggregating 1,233 courses from several open courseware sites, our project solves the problem of users having to manually search through multiple sites to find relevant courses. This not only saves time but also ensures that users have access to a comprehensive range of options. 


##### Areas for Improvement

We have identified several areas for improvement in our project: 

    - Expand Dataset: We plan to expand the number of open courseware sites we scrape to ensure a more comprehensive dataset.
    - Prompt Engineering Experimentation: We intend to experiment with prompt engineering techniques to enhance the quality of our search results.
    - Alternative Similarity Metrics Exploration: We plan to explore alternative similarity metrics beyond Cosine, as it could lead to better results.
    - User Feedback Incorporation: We hope to incorporate user feedback by conducting evaluations to help us refine our approach to ensure it satisfies user needs.


#### Future Work

We intend to continue this project by developing an LLM Retrieval Augmented Generation ChatBot that empowers people to achieve their goals by generating personalized learning pathways consisting of open-access courses tailored to individuals' specific backgrounds, needs, and ambitions. The system will additionally allow the user to provide feedback on the generated learning path, which can be used to further refine the recommendations. 


