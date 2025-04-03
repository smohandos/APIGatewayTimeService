# APIGatewayTimeService

Speaking Clock - README

Overview

This application provides a service to convert time in the 24-hour format into words. 
It also supports handling user input in the "HH:mm" format, returning the corresponding time in words.
Example: "08:34" → "It's eight thirty four"
Special Cases: "12:00" → "It's Midday", "00:00" → "It's Midnight"

API Gateway is the front facing application and connects with Time Input Service which in turn connects with Time Conversion Service.

Requirements

1. Java: JDK 8 or above

2. Maven: For building and managing the project

3. Spring Boot: Framework used for microservice development

4. JUnit: For unit testing

Setup Instructions

git clone https://github.com/smohandos/APIGatewayTimeService.git
cd APIGatewayTimeService
mvn clean install
mvn spring-boot:run

git clone https://github.com/smohandos/TimeInputService.git
cd TimeInputService
mvn clean install
mvn spring-boot:run

git clone https://github.com/smohandos/TimeConversionService.git
cd TimeConversionService
mvn clean install
mvn spring-boot:run

API Endpoints

The application exposes the following REST endpoints:
1. Get Current Time in Words
Description: Returns the current time converted to words in the 24-hour format.
Endpoint: GET http://localhost:8080/currentTime
Example Response: "It's eight thirty four"

2. Convert User Input Time to Words
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

