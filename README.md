# Enhancing Rail Madad with AI-Powered Complaint Management


  
## Contributors

- **Sneha Jain**
- **Siddhartha Chakrabarty**
- **Sakshi Salunke**   
- **Pratham Gadkari**  
- **Suraj Chavan**  
- **Anuj Tadkase**  


## Index

1. [Problem Statement](#1-problem-statement)  
2. [Issues in Current System and Our Solution](#2-issues-in-current-system-and-our-solution)  
3. [Core Objectives](#3-core-objectives)  
4. [Architecture](#4-architecture)  
5. [Methodology and Tech Stack](#5-methodology-and-tech-stack)  
6. [Automated Routing Process](#6-automated-routing-process)  
7. [Methodology and Unique Selling Points (USPs)](#7-methodology-and-unique-selling-points-usps)  
8. [Demo Link and Implementation Images](#8-demo-link-and-implementation-images)  
9. [Implementation Images](#9-implementation-images)

## 1. Problem Statement
![image](https://github.com/user-attachments/assets/93183a5b-2ca5-4ae7-adbd-21f71496c5b6)

## 2. Issues in Current System and Our Solution

**Problems in Current System**  
- Complaints are manually categorized and routed, leading to delays in resolution.  
- No analysis of customer sentiment, urgency, or recurring issues.  
- Lack of effective processing for multimedia complaints (photos and videos).

**Our Solution**  
- Centralized AI-powered system for automated categorization, routing, and analysis.  
- Real-time sentiment and urgency detection.  
- Integration of multimedia processing capabilities.

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

## 3. Core Objectives

- Reduce complaint response and resolution time by 50%.  
- Simplify categorization and routing using AI for faster grievance redressal.  

![Core Objectives](https://github.com/user-attachments/assets/8a784dc0-562a-49d7-a220-69ac23706045)

## 4. Architecture

![Architecture](https://github.com/user-attachments/assets/9e45318b-d241-4421-abf4-aec6fee8d061)

## 5. Methodology and Tech Stack

![Methodology and Tech Stack](https://github.com/user-attachments/assets/64b80809-c3e6-438a-8098-f3c27f99644a)

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

## 6. Automated Routing Process

- **Complaint Categorization**: Complaints are categorized by train and station.  
- **Routing**: Complaints are routed to TTEs or Station Masters for initial resolution. If unresolved, they are forwarded to relevant departments.  
- **Escalation**: If the complaint remains unresolved within 5-10 minutes, it is automatically escalated to the Division Office for further action.  
- **Automatic Rerouting**: If the TTE declares the issue unsolvable, the complaint is rerouted to the appropriate department for resolution.

## 7. Methodology and Unique Selling Points (USPs)

### Input Considerations

The system supports multiple types of inputs for complaint registration:

- **Twitter/Social Media Posts**:  
   Complaints or feedback from social media platforms like Twitter are integrated.  
   [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/tweets.py)  

- **Image Inputs**:  
   The system allows users to submit image-based complaints.  
   [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/image.py)  

- **Video Inputs**:  
   Video complaints or feedback can be uploaded directly into the system.  
   [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/video.py)  

- **Voice Inputs**:  
   Users can also register complaints via voice input, with audio being converted to text.  
   [View Implementation](https://github.com/JainSneha6/RailMadad/blob/main/backend/models/voice.py)

### Data Extraction

The system employs advanced data extraction techniques to process input from various formats:

#### Data Extraction from Voice

- **Voice Data**: Using **DistilBERT**, a lightweight version of BERT, the system processes audio complaints.  
- **Noise Reduction**: Noise reduction algorithms ensure that only relevant customer content is retained for analysis.

![DistilBERT Comparison](https://github.com/user-attachments/assets/20f6f611-61a9-4e55-aa8f-7e717170a23e)

#### Data Extraction from Text, Images, and Videos

- **Text & Visual Data**: For image and video complaints, the system uses **YOLOv5**, based on ResNet, for object detection and analysis.  
- **Data Input Sources**: The system directly integrates inputs from RailMadad's official Twitter handle and app for processing.

![YOLOv5 Architecture](https://github.com/user-attachments/assets/70982645-68bc-4d45-a395-84d34e270d41)

### Complaint Resolution and Forwarding

- **Complaint Categorization**: Complaints are first categorized based on the nature of the issue and forwarded to the appropriate TTE.  
- **Dynamic Resolution Steps**: TTEs receive dynamically generated steps for resolving complaints, utilizing **Gemini** and **Llama 2** for accurate guidance.  
- **Rerouting**: If unresolved by the TTE, complaints are automatically rerouted to the appropriate department using natural language processing techniques.

![Routing Process](https://github.com/user-attachments/assets/1a9eb66a-2a6e-451e-ae98-2c3c9afdd996)

### Department-Wise Analytics

- **Segmentation**: Complaints are segmented by type, enabling departments to analyze the issues effectively.  
- **Trends Identification**: The system provides detailed analytics, helping departments identify recurring issues and trends.

![Department Analytics](https://github.com/user-attachments/assets/cd2239f0-93b4-40bd-89ab-a2eff2609d5e)

### Chat with Database

- **Natural Language Querying**: The system supports natural language queries to retrieve data from the database.  
- **Integration**: Utilizes **LangChain** with LLMs for context-aware retrieval from **Azure NoSQL** databases.

### Customer Feedback Sentiment Analysis

- **Sentiment Analysis**: Customer feedback is analyzed using **Vader's Sentiment Analyzer**, predicting trends in feedback sentiment.  
- **Improvement**: The analysis helps in identifying patterns to improve complaint resolution processes and customer satisfaction.

### Database Compatibility

- **Seamless Integration**: The system’s database structure is fully aligned with RailMadad’s existing database, ensuring smooth data flow and compatibility.  
- **Scalability**: It supports scalability to handle large volumes of data and growing needs of the system over time.

## 8. Demo Link and Implementation Images

[![Watch the Project Demonstration](https://img.youtube.com/vi/4Ji4QcbaSEg/0.jpg)](https://www.youtube.com/watch?v=4Ji4QcbaSEg)

## 9. Implementation Images

**Home Page**  
![Home Page](https://github.com/user-attachments/assets/3c68c5e0-8307-4c61-8e29-33d47bbe03aa)  

**Grievance Details**  
![Grievance Details](https://github.com/user-attachments/assets/6094b38a-df7e-4fcb-b369-8650c18e8986)  

**Detailed Analytics**  
![Detailed Analytics](https://github.com/user-attachments/assets/f3597a3b-b5c1-4f92-a58a-9f3e0257fbe8)
