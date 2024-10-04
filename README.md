# Trello-API-Automation-with-CI-CD-Part2

## Project Overview
This repository extends the manual API testing from Part 1 by focusing on automating Trello API tests using Newman (Postman’s CLI), integrated with a CI/CD pipeline via Jenkins and Docker. 

The goal is to run automated API tests continuously, ensuring the quality of the Trello API integration in an automated environment.

-----------------------------------

#### Note: This repository builds upon the Postman collection from Trello API Testing with JavaScript (Part 1) but focuses on automation and continuous integration. 
#### If you're unfamiliar with the manual testing setup, please refer to Part 1.

- #### Start Date: Sept. 2024
- #### End Date: Oct. 2024
- #### API Under Test: Trello API

## Tools Used:
- **Postman**: For creating and managing API requests and tests (as prepared in Part 1).

- **Newman**: Is a command-line tool that allows you to execute Postman collections.
- **Jenkins**: To automate the execution of tests as part of a CI/CD pipeline for the Postman Trello API collection.
- **Docker**: Used to containerize the environment, ensuring consistency across different test runs.
- **Node.js**: Required for running Newman.



## CI/CD Pipeline Overview:

In this part, you will:
1.Automate the execution of the Postman collection created in Part 1 using Newman.

2. Use Jenkins to set up a CI/CD pipeline, automating the tests on each code commit or a scheduled basis.

Containerize the testing environment using Docker for consistency across different machines.
Generate test reports directly in Jenkins and review them for quality assurance.
Automating Trello API Testing with Newman:
Newman allows the Postman collection (Trello API Oct.2024.postman_collection.json) to be executed from the command line.
The collection will be automatically run as part of the Jenkins pipeline, providing continuous feedback on the Trello API.
Jenkins Integration:
The repository includes a Jenkinsfile that defines the steps to:
Install dependencies (e.g., Node.js, Newman).
Run the Postman collection using Newman.
Generate and publish test results in Jenkins.
Docker Setup:
Docker ensures that the testing environment is consistent, regardless of where the tests are run.
A Dockerfile is provided to containerize the Node.js and Newman environment, simplifying the CI/CD setup.
Endpoints used with HTTP Methods:
(Same table as Part 1; you can reuse this here.)

How to Use This Repository:
Clone the repository and set up your Jenkins environment.
Build and run the Docker container to ensure consistency in testing.
Use Jenkins to trigger automated tests with Newman.
Review the test results in Jenkins, which provides insights into the success or failure of the Trello API tests.
Continuous feedback can be set up for each commit or as part of a schedule, allowing automated testing to catch issues early.
Screenshots and Example Reports:
Provide screenshots of:

Jenkins job configuration for running the tests.
Sample test results from the Jenkins dashboard.
Docker container setup and logs.
Summary:
Repository B focuses on automating the testing process that was introduced in Part 1.
Automation tools like Newman, Jenkins, and Docker are the main focus of this part, enabling continuous testing in a CI/CD pipeline.
Key Differences Between Part 1 and Part 2:
Part 1 is about manual testing with Postman and JavaScript.
Part 2 extends this into automated testing with a CI/CD pipeline using Newman, Jenkins, and Docker.
