# Enhancing Rail Madad with AI-Powered Complaint Management

---

## Index

1. [Problem Statement](#1-problem-statement)  
2. [Issues in Current System and Our Solution](#2-issues-in-current-system-and-our-solution)  
3. [Core Objectives](#3-core-objectives)  
4. [Architecture](#4-architecture)  
5. [Methodology and Tech Stack](#5-methodology-and-tech-stack)  
6. [Automated Routing Process](#6-automated-routing-process)  
7. [Unique Selling Points (USPs)](#7-unique-selling-points-usps)  
8. [Input Considerations](#8-input-considerations)  
9. [Data Extraction](#9-data-extraction)  
   - [From Voice](#91-data-extraction-from-voice)  
   - [From Text, Images, and Videos](#92-data-extraction-from-text-images-and-videos)  
10. [Complaint Resolution and Forwarding](#10-complaint-resolution-and-forwarding)  
11. [Department-Wise Analytics](#11-department-wise-analytics)  
12. [Chat with Database](#12-chat-with-database)  
13. [Customer Feedback Sentiment Analysis](#13-customer-feedback-sentiment-analysis)  
14. [Database Compatibility](#14-database-compatibility)  
15. [Business Model](#15-business-model)  
16. [Dependencies](#16-dependencies)  
17. [Demo Link and Implementation Images](#17-demo-link-and-implementation-images)  

---

## 1. Problem Statement
![image](https://github.com/user-attachments/assets/93183a5b-2ca5-4ae7-adbd-21f71496c5b6)

### Expected Solution

**1. Automated Categorization and Prioritization**  
   - Integrate the system with the existing Rail Madad platform to streamline the complaint management process.  
   - **Image and Video Analysis**: Use AI-powered image and video recognition to categorize complaints like coach cleanliness, damage, and staff behavior.  
   - **Urgency Detection**: Assess the severity of complaints using visual content and prioritize urgent cases.  

**2. Enhanced Data Extraction**  
   - **Text Recognition (OCR)**: Extract textual information from images/videos (e.g., signage or documents) for more context.  
   - **Metadata Analysis**: Use timestamps and geolocation to provide additional context for resolution.  

**3. Automated Response and Routing**  
   - **AI Chatbots**: Provide instant acknowledgment and gather additional information from complainants.  
   - **Smart Routing**: Route complaints to the most appropriate department using AI algorithms.  

**4. Predictive Maintenance**  
   - **Issue Prediction**: Use machine learning models to predict recurring issues for proactive maintenance.  

**5. Feedback and Continuous Improvement**  
   - **Sentiment Analysis**: Analyze feedback sentiment to identify areas for improvement.  
   - **Performance Monitoring**: Continuously track and optimize the resolution process.  

**6. Training and Support**  
   - **AI-Assisted Training**: Help staff analyze and resolve complaints efficiently using AI tools.  
   - **Resource Allocation**: Dynamically allocate resources based on complaint patterns.

---

## 2. Issues in Current System and Our Solution

**Problems in Current System**  
- Complaints are manually categorized and routed, leading to delays in resolution.  
- No analysis of customer sentiment, urgency, or recurring issues.  
- Lack of effective processing for multimedia complaints (photos and videos).

**Our Solution**  
- Centralized AI-powered system for automated categorization, routing, and analysis.  
- Real-time sentiment and urgency detection.  
- Integration of multimedia processing capabilities.

---

## 3. Core Objectives

- Reduce complaint response and resolution time by 50%.  
- Simplify categorization and routing using AI for faster grievance redressal.  

![Core Objectives](https://github.com/user-attachments/assets/8a784dc0-562a-49d7-a220-69ac23706045)

---

## 4. Architecture

![Architecture](https://github.com/user-attachments/assets/9e45318b-d241-4421-abf4-aec6fee8d061)

---

## 5. Methodology and Tech Stack

**Web Development**  
- Backend: Python (Flask)  
- Frontend: Next.js with Tailwind CSS  

**AI and Machine Learning**  
- Scikit-learn for models  
- Azure Cognitive Services for OCR  
- LangChain and Gemini for RAG operations and fine-tuning  

**Databases**  
- MongoDB Atlas Azure as the main database  
- ChromaDB for vector storage  

**Deployment**  
- Azure Cloud Services and Docker  

![Methodology and Tech Stack](https://github.com/user-attachments/assets/64b80809-c3e6-438a-8098-f3c27f99644a)

---

## 6. Automated Routing Process

- Complaints are categorized by train and station.  
- Routed to TTE or Station Master, then forwarded to relevant departments.  
- If unresolved within 5-10 minutes, escalated to the Division Office.  
- Automatic rerouting if TTE declares an issue unsolvable.  

---

## 7. Unique Selling Points (USPs)

![Unique Selling Points](https://github.com/user-attachments/assets/12a59fc3-0dc4-455a-9feb-0536279c9460)

---

## 8. Input Considerations

**Supported Input Types**  
1. Twitter/Social Media Posts: [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/tweets.py)  
2. Image Inputs: [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/image.py)  
3. Video Inputs: [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/video.py)  
4. Voice Inputs: [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/voice.py)

---

## 9. Data Extraction

### 9.1 Data Extraction from Voice

- Using **DistilBERT**, a lightweight version of BERT.  
- Noise reduction ensures only customer content is processed.  

![DistilBERT Comparison](https://github.com/user-attachments/assets/20f6f611-61a9-4e55-aa8f-7e717170a23e)  

### 9.2 Data Extraction from Text, Images, and Videos

- **YOLOv5** based on ResNet for object detection in images/videos.  
- Direct inputs from RailMadad's Twitter handle and app.  

![YOLOv5 Architecture](https://github.com/user-attachments/assets/70982645-68bc-4d45-a395-84d34e270d41)  

---

## 10. Complaint Resolution and Forwarding

- Complaints categorized by type are sent to TTEs.  
- TTEs receive dynamically generated steps for resolution using Gemini and Llama 2.  
- If unresolved, complaints are rerouted using natural language to appropriate departments.  

![Routing Process](https://github.com/user-attachments/assets/1a9eb66a-2a6e-451e-ae98-2c3c9afdd996)

---

## 11. Department-Wise Analytics

- Complaints are segmented and displayed with detailed analytics.  
- Helps departments identify trends and recurring issues.  

![Department Analytics](https://github.com/user-attachments/assets/cd2239f0-93b4-40bd-89ab-a2eff2609d5e)

---

## 12. Chat with Database

- Enables natural language queries to retrieve data from the database.  
- Integrates LangChain with LLMs for context-aware retrieval from Azure NoSQL.  

---

## 13. Customer Feedback Sentiment Analysis

- Feedback sentiment analyzed using Vader’s Sentiment Analyzer.  
- Predicts trends and improves resolution processes.  

---

## 14. Database Compatibility

- Database structure aligned with RailMadad's for seamless integration.  
- Supports scalability and ensures compatibility.  

---

## 15. Business Model

![Business Model](https://github.com/user-attachments/assets/38f3ef9c-de28-4b73-b878-12f38bfd0527)

---

## 16. Dependencies

- Integration with existing Rail Madad system.  
- Use of synthetic data for testing and validation.  
- Scalable cloud-based database deployment.  

---

## 17. Demo Link and Implementation Images

[Watch the Project Demonstration](https://www.youtube.com/watch?v=4Ji4QcbaSEg)  

**Home Page**  
![Home Page](https://github.com/user-attachments/assets/3c68c5e0-8307-4c61-8e29-33d47bbe03aa)  

**Grievance Details**  
![Grievance Details](https://github.com/user-attachments/assets/6094b38a-df7e-4fcb-b369-8650c18e8986)  

**Detailed Analytics**  
![Detailed Analytics](https://github.com/user-attachments/assets/f3597a3b-b5c1-4f92-a58a-9f3e0257fbe8)  
