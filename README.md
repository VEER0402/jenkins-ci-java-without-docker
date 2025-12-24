# Jenkins CI Pipeline for Java Application (Without Containerization)

## 📌 Overview
This project demonstrates a **traditional Jenkins Continuous Integration (CI) pipeline** for a Java application.  
Jenkins pulls source code from GitHub and performs a Maven build directly on the Jenkins server without using containerization.

This setup represents **legacy and enterprise CI environments** where build tools are installed directly on the CI server and builds are manually or selectively triggered for controlled execution.

---

## 🏗️ Architecture

Developer
|
| Git Commit / Push
v
GitHub Repository
|
| (Manual Trigger)
v
Jenkins CI Server
|
| Maven Build
v
Build Artifact (JAR)


