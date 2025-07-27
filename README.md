# ParkingProjTest
Smart Parking System

A serverless smart parking system using AWS services for automatic license plate recognition, real-time parking management.



Overview:

This project implements a smart parking system with AI. It uses AWS Rekognition for license plate detection and provides real-time updates on parking availability. The system automatically manages entries, exits, and calculates parking fees.


Features:

🎯 Real-time parking space monitoring

📸 Automatic license plate recognition

🔄 Smart entry/exit management

📊 Dynamic status updates


Test Cases:

The /images folder contains test images to demonstrate different scenarios:
image1.jpg, image2.jpg, image3.jpg, image4.jpg and image6.jpg (used for Recognition Failure Test). 


- Entry Test:
  
System responds with "حياك الله", Demonstrates successful entry when spots are available.


Updates the counter.


 - Exit Test:


Displays "في أمان الله".

Shows parking duration and fee details.

Updates the counter.

 - Full Parking Test

   
Tests system response when parking is full
Shows "المعذرة المواقف ممتلئة", Demonstrates capacity management.


 - Recognition Failure Test (image6.jpg):
   
Tests system's response when plate cannot be detected
Shows "نأسف لم نتمكن من التقاط اللوحة", Demonstrates error handling.



Technical Architecture:



  Frontend:
  

HTML5, CSS3, JavaScript.

Real-time status updates.

Responsive design.

File upload handling.



  Backend (AWS Serverless):
  

Lambda:
 
 1-pre-url.py:
Generates secure S3 upload URLs, 
Manages file upload permissions.

 2-AnalyzePlateAPI.py:
Handles status endpoints, 
Manages plate information, 
Real-time counter management.

 3-AnalyzePlateTrigger.py: 
Processes uploaded images, 
Manages entry/exit logic, 
Updates parking status, 
Calculates parking fees, 


AWS Services Used:

AWS Lambda for serverless computing.

Amazon S3 for image storage.

Amazon Rekognition for plate detection.

Amazon DynamoDB for data storage.

AWS API Gateway for REST endpoints.

Route 53 for DNS management.

CloudFront for content delivery.

ACM for SSL/TLS certificates.

WAF for security.


Security Features:

Pre-signed URLs for secure uploads.

Protected API endpoints.

CORS enabled.




WAF protection against:
 ,SQL injection
Cross-site scripting, 
DDoS attacks, 
Rate limiting, 
SSL/TLS encryption, 
Edge location security, 
Performance Features:



Global CDN distribution: 
Edge caching, 
Reduced latency, 
Automatic scaling, 
DDoS protection, 
High availability, 
API Endpoints. 



