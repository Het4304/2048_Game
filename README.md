# Game Application Hosted on AWS Elastic Beanstalk 🚀

## 🌟 Project Overview

This project demonstrates a game application containerized using Docker and hosted on AWS Elastic Beanstalk. The application showcases a scalable and efficient deployment pipeline, leveraging modern cloud and containerization technologies.

---

## 🛠️ Tech Stack

- **Containerization:** Docker
- **Cloud Hosting:** AWS Elastic Beanstalk

---

## 🐳 Dockerfile Details

The `Dockerfile` used for this application includes:
- **Base Image**: [e.g., ubuntu:22.04, Python:3.8-slim]
- **Dependencies Installation**: Installs all required libraries and dependencies.
- **Port Exposure**: Exposes the application port (e.g., `EXPOSE 80`).
- **Application Start**: Specifies the command to start the game application.

### Sample Dockerfile
```dockerfile
FROM Baseimage

# Set the working directory
WORKDIR /app

# Copy application code and install dependencies
COPY . /app
RUN pip install -r requirements.txt

# Expose the application port
EXPOSE 80

# Start the application
CMD ["run app.py"]
```

---

## 🚀 Hosting on AWS Elastic Beanstalk

### Steps to Deploy via AWS Management Console:

1. **Login to AWS Console:**
   - Navigate to the AWS Elastic Beanstalk service.

2. **Create a New Application:**
   - Click on "Create Application."
   - Enter the application name and select the platform (e.g., Docker).

3. **Upload Code:**
   - Upload the source bundle (ZIP file with Dockerfile and application code).

4. **Configure Environment:**
   - Set environment variables and select instance type as needed.

5. **Deploy:**
   - Launch the application and monitor deployment progress.

6. **Access the Application:**
   - Once deployed, use the provided URL to access your application.

---

## 🔍 Testing

- Use `curl` or a web browser to access the game application.

---

## 🛡️ Security Considerations

- **Environment Variables**: Store sensitive data using Elastic Beanstalk environment variables.
- **IAM Roles**: Ensure the Elastic Beanstalk environment has an appropriate IAM role for AWS services.
- **Network Security**: Configure security groups to restrict access.

---

## 📸 Screenshots

### Application Interface:
![Screenshot 1](/Screenshot%202025-01-02%20at%2001.26.16%2019.11.53.png)

### Deployment Configuration:
![Screenshot 2](/Screenshot%202025-01-02%20at%2001.26.27%2019.11.53.png)
