# Game Application Hosted on AWS Elastic Beanstalk 🚀

## 🌟 Project Overview

This project demonstrates a game application containerized using Docker and hosted on AWS Elastic Beanstalk.

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

### Dockerfile
```dockerfile
FROM ubuntu:22.04

RUN apt-get update
RUN apt-get install -y nginx curl zip

RUN echo "daemon off;" >>/etc/nginx/nginx.conf
RUN curl -o /var/www/html/master.zip -L https://codeload.github.com/gabrielecirulli/2048/zip/master

RUN cd /var/www/html/ && unzip master.zip && mv 2048-master/* . && rm -rf 2048-master master.zip

EXPOSE 80

CMD [ "/usr/sbin/nginx","-c","/etc/nginx/nginx.conf"]
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
![Screenshot 1](/1.png)

### Deployment Configuration:
![Screenshot 2](/21.png)



