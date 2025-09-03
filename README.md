HealthRx Hiring Challenge - Spring Boot Solution
This project is a Spring Boot application designed to automate the submission process for the HealthRx hiring challenge. It performs the required API calls on application startup.

Project Structure
pom.xml: Contains all project dependencies, including Spring Boot Web and Lombok.

src/main/resources/application.properties: Configuration file for your user details and API endpoints.

src/main/java/com/example/healthrx/: Main package for the application.

HealthRxHiringChallengeApplication.java: The main entry point of the Spring Boot app.

dto/Dtos.java: Contains all Data Transfer Objects (POJOs) for handling JSON request/response bodies.

service/ApiService.java: A service class dedicated to making the external API calls using RestTemplate.

runner/ChallengeRunner.java: A CommandLineRunner component. This is where the main logic lives. It runs automatically when the application starts.

How to Use
1. Configure Your Details
Open src/main/resources/application.properties and replace the placeholder values with your actual name, registration number, and email.

user.name=Your Name
user.regNo=YOUR_REG_NO
user.email=your.email@example.com

2. Add Your SQL Solution (CRITICAL STEP)
Determine if your regNo's last two digits are odd or even.

Solve the corresponding SQL problem from the Google Drive link provided in the challenge description.

Open src/main/java/com/example/healthrx/runner/ChallengeRunner.java.

Find the getFinalQueryByRegNo method.

Replace the placeholder SQL query with your final, correct query string.

// Inside ChallengeRunner.java

private String getFinalQueryByRegNo(String registrationNumber) {
    // ... logic to check odd/even ...

    if (isOdd) {
        // 🚨 REPLACE THIS STRING WITH YOUR SOLUTION FOR THE ODD-NUMBER QUESTION
        return "SELECT ... your final query for question 1 ...;";
    } else {
        // 🚨 REPLACE THIS STRING WITH YOUR SOLUTION FOR THE EVEN-NUMBER QUESTION
        return "SELECT ... your final query for question 2 ...;";
    }
}

3. Build the Project
Navigate to the root directory of the project in your terminal and run the following Maven command. This will compile the code and package it into a .jar file.

mvn clean package

This will create a JAR file in the target/ directory (e.g., healthrx-hiring-challenge-0.0.1-SNAPSHOT.jar). This is the file you need to submit.

4. Run the Application
To run the application and trigger the API calls, use the following command:

java -jar target/healthrx-hiring-challenge-0.0.1-SNAPSHOT.jar

The application will start, run the logic defined in ChallengeRunner, print logs to the console, and then exit.
