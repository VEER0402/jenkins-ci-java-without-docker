# Jenkins CI Pipeline for Java Application (Without Containerization)

## 📌 Overview
This project demonstrates a **traditional Jenkins Continuous Integration (CI) pipeline** for a Java application.  
Jenkins pulls source code from GitHub and performs a Maven build directly on the Jenkins server without using containerization.

This setup represents **legacy and enterprise CI environments** where build tools are installed directly on the CI server and builds are manually or selectively triggered for controlled execution.

---

## 🏗️ Architecture

<img width="1024" height="1024" alt="img" src="https://github.com/user-attachments/assets/fe4de6b0-972d-45a1-8047-734e87bffcb9" />




---

## 🛠️ Technologies Used

- **Jenkins** – CI automation server
- **GitHub** – Source code management
- **Java 17** – Application runtime
- **Apache Maven** – Build and dependency management
- **Ubuntu Linux (EC2)** – Jenkins host server

---

## ⚙️ Jenkins Pipeline Details

The CI pipeline is defined using a **Declarative Jenkinsfile** stored in the root of the repository.

### Pipeline Stages:
1. **Checkout Code**
   - Jenkins pulls the latest source code from GitHub.
2. **Build with Maven**
   - Maven compiles the application and packages it into a JAR file.
3. **Post-build Status**
   - Jenkins reports build success or failure.

---

## 📄 Jenkinsfile

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL'
        }
        failure {
            echo 'BUILD FAILED'
        }
    }
}


🚀 How the CI Process Works

Developer pushes code to GitHub.

Jenkins job is manually triggered (controlled execution).

Jenkins fetches the repository.

Maven builds the Java application on the Jenkins server.

Build artifacts are generated in the target/ directory.





🔍 Why Manual Triggering?

This pipeline uses manual triggering to reflect real-world enterprise scenarios where:

Deployments are tightly controlled.

Shared infrastructure is used.

Automatic triggers may introduce risk.

Builds are executed only after validation or approval.

The pipeline can be easily extended to auto-trigger using GitHub webhooks if required.






📈 Key Highlights

Traditional CI pipeline without containerization

Jenkinsfile managed as code

Enterprise-style controlled build execution

Clear separation of CI logic and application code

Easily extendable to Docker or webhook-based automation
