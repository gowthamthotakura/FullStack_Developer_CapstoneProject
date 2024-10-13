
![image](https://github.com/user-attachments/assets/ea35b8e5-230f-44f3-a37e-530518ae10a3)


 
Architecture Overview
The final project for this course has several steps. The project is divided into smaller labs, with detailed instructions for each step. I must complete all labs to complete the project successfully.

Project breakdown:
1.	Fork the repository into my account.
2.	Clone the repository in the Cloud IDE environment.
3.	Create static pages to finish the user stories.
4.	Run the application locally.
   
Add user management to the Django application:
1.	I am implementing user management using the Django user authentication system and creating a REACT frontend.
   
Implement backend services:
1.	I am creating a Node.js server to manage dealers and reviews using MongoDB and dockerize it.
2.	Deployed sentiment analyzer on Code Engine.
3.	Creating Django models and views to manage car models and car make.
4.	Creating Django proxy services and views to integrate dealers and reviews.

Add dynamic pages with Django templates:
1.	Creating a page that displays all the dealers.
2.	Creating a page that displays reviews for a selected dealer.
3.	Creating a page that lets the end user add a review for a selected dealer.

Implement CI/CD, and then run and test your application:
1.	Setting up continuous integration and delivery for code linting.
2.	Testing my application on Cloud IDE.
3.	Testing the updated application locally.
4.	Deploy the application on Kubernetes.

Solution architecture:
The solution will consist of multiple technologies
1.	The user interacts with the "Dealerships Website", a Django website, through a web browser.

2.	The Django application provides the following microservices for the end user:
•	get_cars/ - To get the list of cars from
•	get_dealers/ - To get the list of dealers
•	get_dealers/:state - To get dealers by state
•	dealer/:id - To get dealer by id
•	review/dealer/:id - To get reviews specific to a dealer
•	add_review/ - To post a review about a dealer

3.	The Django application uses SQLite database to store the Car Make and the Car Model data.

4.	The "Dealerships and Reviews Service" is an Express Mongo service running in a Docker container. It provides the following services:
•	/fetchDealers - To fetch the dealers
•	/fetchDealer/:id - To fetch the dealer by id
•	fetchReviews - To fetch all the reviews
•	fetchReview/dealer/:id - To fetch reviews for a dealer by id
•	/insertReview - To insert a review

5.	"Dealerships Website" interacts with the "Dealership and Reviews Service" through the "Django Proxy Service" contained within the Django Application.

6.	The "Sentiment Analyzer Service" is deployed on IBM Cloud Code Engine, it provides the following service:
•	/analyze/:text - To analyze the sentiment of the text passed. It returns positive, negative or neutral.

7.	The "Dealerships Website" consumes the "Sentiment Analyzer Service" to analyze the feelings of the reviews through the Django Proxy contained within the Django application.




