Spring Boot Quiz API
Table of Contents
Introduction
Features
Technologies Used
API Endpoints
How to Run the Project
Database Configuration
Future Enhancements
Introduction
Welcome to the Spring Boot Quiz API project! This application provides a RESTful API for managing quiz questions and conducting quizzes. Users can add quiz questions, retrieve them by category, and take quizzes while receiving scores based on their answers.
Features
Add Quiz Questions: Users can add a question along with its category.
Get Quiz by Category: Retrieve all quiz questions within a specific category.
Get Quiz by Category and Number of Questions: Fetch a specified number of questions from a chosen category.
Submit Answers and Get Score: Accept user answers, calculate the score, and return the results.
Technologies Used
Java: The backend logic is implemented in Java.
Spring Boot: The REST API is developed using the Spring Boot framework.
PostgreSQL: Used for database management and storage.
Postman: Utilized for API testing and interaction.
API Endpoints
Add a Question
POST /questions
Adds a new quiz question along with its category.
Request Body Example:
json
{
  "category": "Science",
  "question": "What is the chemical symbol for water?",
  "options": ["H2O", "O2", "CO2", "N2"],
  "correctAnswer": "H2O"
}

Get Quiz by Category
GET /quiz/{category}
Retrieves all questions belonging to a specific category.
Path Parameter:
category: The quiz category (e.g., Science).
Get Quiz by Category and Question Count
GET /quiz/{category}/{count}
Retrieves a limited number of questions for a given category.
Path Parameters:
category: The quiz category.
count: The number of questions for the quiz.
Submit Answers and Get Score
POST /quiz/submit
Submits answers for the quiz and returns the score based on correct responses.
Request Body Example:
json
{
  "category": "Science",
  "answers": [
    {"questionId": 1, "answer": "H2O"},
    {"questionId": 2, "answer": "O2"}
  ]
}

Response Example:
json
{
  "totalQuestions": 2,
  "correctAnswers": 1,
  "score": 50
}

How to Run the Project
Clone the repository:
bash
git clone https://github.com/yourusername/quiz-api.git

Navigate to the project directory:
bash
cd quiz-api

Run the project using Maven:
bash
mvn spring-boot:run

Test the APIs using Postman or any API testing tool.
Database Configuration
Ensure PostgreSQL is set up and update the database connection settings in application.properties:
text
spring.datasource.url=jdbc:postgresql://localhost:5432/quizdb
spring.datasource.username=yourusername
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update

Future Enhancements
Implement user authentication for quiz access.
Add timer functionality for each question.
Develop leaderboard functionality to track top scorers.
