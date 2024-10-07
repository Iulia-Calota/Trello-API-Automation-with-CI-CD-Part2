# Trello-API-Automation-with-CI-CD-Part2

## Project Overview
This repository focuses on automating Trello API testing using Newman (Postman’s CLI) and integrating it into a CI/CD pipeline with Jenkins and Docker. It builds upon the manual testing phase from Part 1, transitioning to continuous automated testing.

The goal is to run automated API tests continuously, ensuring the quality of the Trello API integration in an automated environment.

-----------------------------------

#### Note: This repository builds upon the Postman collection from Trello API Testing with JavaScript (Part 1) but focuses on automation and continuous integration. 

- #### Start Date: Sept. 2024
- #### End Date: Oct. 2024

## API Under Test: Trello API

## Tools Used:
- **Postman**: For creating and managing API requests and tests (as prepared in Part 1).
- **PostmanCLI**: Automate using Postman’s command-line tool.
- **Newman**: Is a command-line tool that allows you to execute Postman collections.
- **Jenkins**: To automate the execution of tests as part of a CI/CD pipeline for the Postman Trello API collection.
- **Docker**: Used to containerize the environment, ensuring consistency across different test runs.
- **Node.js**: Required for running Newman.

## Setting Up Trello API Integration
To test the endpoints in this collection, you will need a Trello account. You can [Sign up for free]( https://trello.com/)
1. To authenticate your API requests, you need to generate a Trello API Key and Token:
   - [How to get Trello API Key](https://developer.atlassian.com/cloud/trello/guides/rest-api/authorization/)


 ## Endpoints used with HTTP Method:

| HTTP Method | Endpoint Description      | API Documentation Link                                               |  
|-------------|---------------------------|---------------------------------------------------------------------|
| POST        | Create board              | [Trello API - Create Board](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-id-post) |
| GET         | Get all Boards            | [Trello API - Get Boards](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-get)  |
| GET         | Get single Board          | [Trello API - Get Board](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-id-get)  |
| POST        | Create To Do list         | [Trello API - Create List](https://developer.atlassian.com/cloud/trello/rest/api-group-lists/#api-lists-id-post)  |  
| POST        | Create Done list          | [Trello API - Create List](https://developer.atlassian.com/cloud/trello/rest/api-group-lists/#api-lists-id-post)  |  
| POST        | Create a Card             | [Trello API - Create Card](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-id-post)  |  
| PUT         | Update card               | [Trello API - Update Card](https://developer.atlassian.com/cloud/trello/rest/api-group-cards/#api-cards-id-put)  | 
| DELETE      | Delete a Board            | [Trello API - Delete Board](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-id-delete) |  
| GET         | Get a deleted Board       | [Trello API - Get Deleted Board](https://developer.atlassian.com/cloud/trello/rest/api-group-boards/#api-boards-id-get) | 


## Postman Collection Overview:
This repository contains the **Trello API Oct.2024.postman_collection.json**, designed for manual testing of Trello API endpoints using various HTTP methods. JavaScript scripts in Postman utilize variables to efficiently handle query and path parameters.


## CI/CD Pipeline Overview:
- Automate the execution of the Postman collection created in Part 1 using Newman and CLI from Postman.
- Use Jenkins to set up a CI/CD pipeline, automating the tests on each code commit or a scheduled basis.
- Generate test reports directly in Jenkins and review them for quality assurance.
- Review test results.

## Content:
**A)** Postman Collection Run Using PowerShell Terminal with CLI 

**B)** Postman Collection Run Using PowerShell Terminal with Newman
      - Includes HTML report generated using Newman HTML Extra.

**C)** Test Results and Generated Reports from the Jenkins Dashboard
      - The Jenkins dashboard displays the test results from the Trello API collection, showing the status of each test case (passed or failed) along with detailed logs.

**D)** Trello API -Newman - Jenkinsfile reports from Jenkins      

**A)** This section outlines the execution of the Trello API Collection using the Postman CLI in a PowerShell terminal. This automation process enables efficient running of API tests and generates a comprehensive test report.

#### Note: After the test reports are generated, the results are stored in Postman, allowing for further analysis and debugging.
 ![CLI Run](<Images/Report CLI run to Postman Cloud.png>)
 

**B)** The report is generated using Newman based on the Trello API collection.
![Newman Run](<Images/Report Newman run from Postman.png>)

- HTML report generated using Newman HTML Extra

![HTMLExtra Report](<Images/Newman Run HTML extra Report.png>)


**C)** Jenkins Pipeline for Trello API Testing
pipeline {
  agent any
  
  environment {
      POSTMAN_API_KEY = credentials("postman-api-key")
  }

  stages {

    stage('Postman CLI Login') {
      steps {
        sh 'postman login --with-api-key $POSTMAN_API_KEY'
      }
    }

    stage('Running collection') {
      steps {
        sh 'postman collection run "YOUR COLLECTION ID"'
      }
    }
  }
}

Test results Trello API - Postman CLI - Jenkinsfile:
![Jenkins file](<Images/Trello API - Postman CLI - Jenkinsfile.png>)



**D)** Trello API -Newman - Jenkins
![Newman](<Images/Trello API -Newman - Jenkinsfile.png>)


## Conclusion:
This project successfully implemented automated testing for the Trello API using various methods:

A) The Postman collection was run using the CLI in the PowerShell terminal, demonstrating effective command-line execution.
B) The collection was also executed with Newman in PowerShell, generating detailed HTML reports for comprehensive analysis.
C) Jenkins provided a clear dashboard showcasing the test results, highlighting the status of each test case with detailed logs for debugging.
D) The integration of Newman with Jenkins through the Jenkinsfile ensured smooth automation, resulting in consistent reporting of test outcomes.

Overall, all 37 tests were executed successfully, validating the functionality and reliability of the Trello API.
