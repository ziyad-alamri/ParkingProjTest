# Smart Parking System

A serverless smart parking application that leverages AWS services for automatic license plate recognition and real-time parking management.

---

## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [Test Cases](#test-cases)  
- [Technical Architecture](#technical-architecture)  
  - [Frontend](#frontend)  
  - [Backend (AWS Serverless)](#backend-aws-serverless)  
- [Security Features](#security-features)  
- [Performance Features](#performance-features)  

---

## Overview

This project implements a smart parking system with AI-driven license plate detection and live updates on parking availability. It automatically handles vehicle entries and exits, calculates fees, and keeps track of occupied spaces in real time.

---

## Features

- 🎯 **Real-time parking space monitoring**  
- 📸 **Automatic license plate recognition**  
- 🔄 **Smart entry/exit management**  
- 📊 **Dynamic status updates**  

---

## Test Cases

The `images/` folder contains test images for these scenarios:

- **Entry, Exit & Full Parking Tests**  
  - **Test images:** `image1.jpg`, `image2.jpg`, `image3.jpg`, `image4.jpg`  
  - **Scenarios:**  
    - **Entry Test:** responds with “حياك الله” and increments the counter.  
    - **Exit Test:** shows “في أمان الله”, displays parking duration & fee, updates the counter.  
    - **Full Parking Test:** shows “المعذرة المواقف ممتلئة” when capacity is full.

- **Recognition Failure Test**  
  - **Test image:** `image6.jpg`  
  - **Scenario:** shows “نأسف لم نتمكن من التقاط اللوحة” when plate detection fails.

---

## Technical Architecture

### Frontend

- Built with **HTML5**, **CSS3**, and **JavaScript**  
- Responsive design with real-time status updates  
- File upload handling for entry/exit images  

#### AWS Services Used (Frontend)

- **Amazon S3** – static website hosting  
- **Amazon CloudFront** – content delivery  
- **Route 53** – DNS management  
- **ACM** – SSL/TLS certificates  
- **WAF** – web application firewall  

---

### Backend (AWS Serverless)

- **AWS Lambda – serverless compute**  
  - **1-pre-url.py**  
    - Generates secure S3 upload URLs  
    - Manages upload permissions  
  - **2-AnalyzePlateAPI.py**  
    - Exposes status endpoints  
    - Manages plate information and real-time counters  
  - **3-AnalyzePlateTrigger.py**  
    - Processes uploaded images  
    - Handles entry/exit logic, status updates, and fee calculations  

- **Amazon S3** – image storage & upload triggers  
- **Amazon Rekognition** – license plate detection  
- **Amazon DynamoDB** – session data store  
- **AWS API Gateway** – HTTP endpoints  

---

## Security Features

- 🔐 **Pre-signed URLs** for secure uploads  
- 🔒 **Protected API endpoints**  
- 🌐 **CORS** enabled for approved origins  
- 🛡️ **WAF protection** against:  
  - SQL injection  
  - Cross-site scripting (XSS)  
  - DDoS attacks  
  - Rate limiting  
- 🔏 **SSL/TLS encryption** at the edge  

---

## Performance Features

**Powered by Amazon CloudFront**

- 🌐 **Global CDN distribution** with edge caching  
- ⚡ **Reduced latency** for faster content delivery  
- 🔄 **Automatic scaling** to handle high traffic volumes  
- 🛡️ **Built‑in DDoS protection** and high availability  
  
