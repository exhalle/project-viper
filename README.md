# 🚀📦🔧 Automated CI/CD Project with Jenkins 🔧📦🚀

**🎉💻💡 Introduction 💡💻🎉**

This project aims to automate the Continuous Integration (CI) and Continuous Deployment (CD) process using Jenkins, allowing seamless integration, build, and deployment of a Java app. The following steps describe the process in detail:

**🔧💼👷 How it Works 👷💼🔧**

1. Clone the Java app project from GitHub repository.
2. Utilize Maven to build the app from the "developer" branch, generating necessary artifacts.
3. Build Docker images for the following containers:
    - 🔧🍃🚀 **Tomcat Java Application**: Hosting the Java app.
    - 🔧🐬📦 **MySQL Database**: Configured with an initialized table for the app.
4. Utilize Docker Compose to orchestrate and combine these containers for smooth deployment.
