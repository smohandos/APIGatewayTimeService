# APIGatewayTimeService

Speaking Clock - README

Overview

This application provides a service to convert time in the 24-hour format into words. It also supports handling user input in the "HH:mm" format, returning the corresponding time in words.
Example: "08:34" → "It's eight thirty four"
Special Cases: "12:00" → "It's Midday", "00:00" → "It's Midnight"

API Gateway is the front facing application and connects with Time Input Service which in turn connects with Time Conversion Service.

Requirements

1. Java: JDK 8 or above

2. Maven: For building and managing the project

3. Spring Boot: Framework used for microservice development

4. JUnit: For unit testing

Setup Instructions

1. Clone the repository
git clone https://github.com/yourusername/speaking-clock.git
cd speaking-clock
2. Build the project using Maven
If you don't have Maven installed, you can download it from here or install it via a package manager (e.g., Homebrew for macOS).
To build the project, run:
mvn clean install
This will compile the source code, run tests, and package the application into a deployable artifact (e.g., JAR file).
3. Run the application
After building, you can run the application using the following command:
mvn spring-boot:run
Alternatively, if you prefer to run the packaged .jar file (after building it), you can use:
java -jar target/speaking-clock-1.0.0.jar
This will start the application on the default port (8080).
API Endpoints

The application exposes the following REST endpoints:
1. Get Current Time in Words
Endpoint: GET http://localhost:8080/currentTime
Description: Returns the current time converted to words in the 24-hour format.
Example Response: "It's eight thirty four"
2. Convert User Input Time to Words
Endpoint: GET http://localhost:8080/userInputTime
Parameters:
time: A string representing the time in "HH:mm" format.
Description: Converts the given time (in 24-hour format) to words.
Example: GET http://localhost:8080/userInputTime?time=11:25
Example Response: "It's eleven twenty five"
3. Special Cases
Midday: If the time is "12:00", the response will be "It's Midday".
Midnight: If the time is "00:00", the response will be "It's Midnight".

There are a total of 3 services
1. API Gateway Time Service
2. Time Input Service
3. Time Conversion Service

Build and Deployment

Building the project:
To build the project from the source, use the following Maven command:
mvn clean install
This will:
Clean the project (remove previously compiled files).
Install dependencies.
Run unit tests.
Package the application into a deployable .jar file located in the target/ directory.
Deploying the Application:
The application is packaged as a .jar file. To deploy, run:
java -jar target/speaking-clock-1.0.0.jar
This will start the application locally on port 8080 by default.
