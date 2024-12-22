## Enhancing Rail Madad with Al-powered Complaint Management


## Problem Statement:

Expected Solution: 
1. Automated Categorization and Prioritization: 
Integrate the system with the existing Rail Madad platform to streamline the complaint management process. 
Image and Video Analysis: Use Al-powered image and video recognition to automatically categorize the nature of the complaint (e.g., coach cleanliness, damage, staff behaviour). 
Urgency Detection: Implement Al to assess the severity of the issue from visual content and prioritize complaints that need immediate attention. 
2. Enhanced Data Extraction: 
Text Recognition (OCR): Utilize Optical Character Recognition (OCR) to extract textual information from images or videos, such as signage or documents, to gather more contexts about the complaint. 
Metadata Analysis: Extract metadata from images and videos (e.g., timestamp, location) to provide additional information for more accurate and quicker resolution. 
3. Automated Response and Routing: 
AI Chatbots: Deploy Al chatbots to provide instant acknowledgment and preliminary responses, collecting additional necessary information from the complainant. 
Smart Routing: Use Al algorithms to route complaints to the most appropriate department or official based on the content of the photos or videos. 
4. Predictive Maintenance: 
Issue Prediction: Implement machine learning models to predict recurring issues from the analysis of visual data trends, helping in proactive maintenance and reducing future complaints.
 5. Feedback and Continuous Improvement: 
Sentiment Analysis: Use Al to analyze the sentiment of feedback provided by complainants, identifying areas needing improvement. 
Performance Monitoring: Continuously monitor the effectiveness of the complaint resolution process through Al-driven analytics, making data-driven adjustments for process enhancement. 
Accuracy detection: Accuracy of Al-powered complaint detection can be analysed. 
Speed Analysis: Speed of complaint registration and resolution. ? User experience and satisfaction. 
Scalability and integrability with existing system. 
6. Training and Support: 
Al-Assisted Training: Provide Al-based training tools for staff to help them better analyze and resolve complaints efficiently using visual data. 
Resource Allocation: Use Al to analyze complaint patterns and allocates resources dynamically, ensuring that high-priority issues receive prompt attention. 



## Problem with current system and our Solution

Currently the RailMadad architecture is such that all complaints have to be manually categorized and then routed to the specific responsible department leading to delays in grievance resolution. 
There is no proper provision for analyzing customer sentiment, urgency & recurring issues. 
A significant portion of daily complaints includes multimedia files such as photos and videos, whose information needs to be extracted properly.
Our solution aims to provide a centralized platform for addressing all these issues using an AI powered categorization and routing system.


# Core objectives of our Project:
![image](https://github.com/user-attachments/assets/8a784dc0-562a-49d7-a220-69ac23706045)

Our solution aims to reduce both the response and disposal time by half. 
Our aim is to simplify the categorization and routing process using AI based techniques to enable fast grievance redressal. 


# Architecture

![image](https://github.com/user-attachments/assets/9e45318b-d241-4421-abf4-aec6fee8d061)



# METHODOLOGY and TechSTACK
![image](https://github.com/user-attachments/assets/64b80809-c3e6-438a-8098-f3c27f99644a)
Webdev:
We have used the Python based framework Flask for the backend & Next JS for the frontend along with Tailwind CSS for the UI.
GenAI/ML
Scikit-Learn has been used for creating the ML models & Azure Cognitive Services has been used for the OCR technologies. We have used Langchain and Gemini for performing the RAG operations & fine-tuning.
Databases
We have used MongoDB Atlas Azure as the main database & Chroma DB for the Vector database for RAGs.
Deployment
We are using Azure Cloud Services & Docker for deployment on the cloud.




AUTOMATED ROUTING PROCESS : 


The complaint routing process works by first categorizing complaints according to Train & Station .
 Then sending the complaints to the TTE and Station Master respectively who then forward it to the respective contractors or departments.
If its a train related incident which the tte cannot sort, tte can route it to upcoming station, it will automatically be routed when tte declares that problem is unsolvable.
 Also, if the complaint is not acknowledged within 5-10 minutes, then it is sent to the Division Office for further action. 
At each routing department incharge of the complaint is aware of the issue, and once its declared unsolvable the respective department can take it in their hand.


USPs :


Our plan is explained in detail below. Following are the unique selling points of our solution: 

![image](https://github.com/user-attachments/assets/12a59fc3-0dc4-455a-9feb-0536279c9460)


Input  Considerations :

All input types which we have implemented : 

Twitter/ Social Media Post inputs
https://github.com/JainSneha6/RailMadad/blob/main/backend/models/tweets.py


Image inputs
https://github.com/JainSneha6/RailMadad/blob/main/backend/models/image.py


Video inputs
https://github.com/JainSneha6/RailMadad/blob/main/backend/models/video.py


Voice inputs
https://github.com/JainSneha6/RailMadad/blob/main/backend/models/voice.py



![image](https://github.com/user-attachments/assets/b71700d8-65eb-44a3-b289-e4ea7e97a520)


Data Extraction From Voice  :


We intend to do this by using the DistilBERT model which is a lighter and distilled version of the BERT Transformer model. 

Why  DistilBERT you may ask??
What we want to do through this is to find urgency/sentiment and also remove noise from the background through this model, so whenever customer is speaking only their content would be stored without the noise.

Following is a detailed comparison of DistilBERT with other models:

![image](https://github.com/user-attachments/assets/20f6f611-61a9-4e55-aa8f-7e717170a23e)

![image](https://github.com/user-attachments/assets/d0839ee1-870b-4de6-918b-bcf3b9897aa6)

Data Extraction From Text,Images,Videos  :
There are a lot of image inputs in RailMadad platforms and also video inputs from social media, for extraction of content through those images we need to make sure that we use proper models
Further on inputs are also directly taken from the RailMadad twitter handle as well as the RailMadad app and website which include multimedia like photos , videos etc
This is followed by Data Extraction from the complaints using Multimedia processing. 
We are performing this by utilizing a fine tuned YOLOv5 model based on the ResNet architecture. 
Our intention behind using YOLOv5 is to detect key objects and contexts in the images and then categorize them accordingly. 

![image](https://github.com/user-attachments/assets/70982645-68bc-4d45-a395-84d34e270d41)
![image](https://github.com/user-attachments/assets/98c84e3b-d2d5-45e2-8537-6b1da5695b36)




Complaint Resolution & Forwarding :
After the categorization process, the complaints are sent to the TTEs and they are provided with detailed steps to resolve the issues generated dynamically using Gemini & a fine-tuned Llama 2 AI model
If the complaint is not resolved on the TTE side, then he has the option to route it using natural language to specific departments responsible for the specific stations.

![image](https://github.com/user-attachments/assets/81cf6245-0f02-4573-a3bf-334869bb5fa5)

This entire routing through natural language is performed using Langchain and LLMs which interact with the database to extract information.

![image](https://github.com/user-attachments/assets/1a9eb66a-2a6e-451e-ae98-2c3c9afdd996)

![image](https://github.com/user-attachments/assets/82675eea-958c-485f-ac7a-6dc44fa48033)

Moreover, we have used specific datasets and synthetic data which is in accordance with what the Railways currently use to enable easy integration with the existing architecture. 
Department Wise Analytics :
![image](https://github.com/user-attachments/assets/cd2239f0-93b4-40bd-89ab-a2eff2609d5e)

Proper complaint segmentation has been performed and detailed department wise analytics displayed for easier visualization of trends and preventing recurring issues.


Chat with Database :
Natural language chat with the database has been integrated to get required data from the database without the hassle required with conventional methods of filtering and manual retrieval. 
The LLM model has been used in pairing with Langchain to perform proper context generation from the chat and then implement retrieval from the Azure NoSQL database.
So just in case the department wants to do analytics for daily data or some time specific data they can do that easily using this chat with database feature 


Customer Feedback Sentiment Analysis :
After successful resolution of complaints, customers are asked for feedback regarding the resolution process. 
The feedback is then analyzed using Vader’s Sentiment Analyzer model for detecting the sentiment(Positive, Negative, Neutral). 
Depending on the sentiment, further analysis is performed to predict trends and prevent recurring issues.

![image](https://github.com/user-attachments/assets/d3a91399-c429-425a-b85e-25ad8ba4e046)


Use of similar database for Compatibility :
The structure of our database has been kept similar to what is used by the Railways currently to ensure compatibility & easy integration. 
![image](https://github.com/user-attachments/assets/2697d21e-af70-4357-b8e8-dcfb97015bf1) 
![image](https://github.com/user-attachments/assets/42fb278c-e043-4f0f-849a-2b494c8e50af)
![image](https://github.com/user-attachments/assets/7c5f5371-cb46-4d7c-b46b-330bb5de99ff)

Business Model:
Business Deployment Model :
Our Business Deployment model is majorly based on the following two layers described below :

![image](https://github.com/user-attachments/assets/38f3ef9c-de28-4b73-b878-12f38bfd0527)

Dependencies :

Integration with rail-madad existing system
We have made sure that the data, and databases are similar to rail-madad, and all the models are made in a way in which it integrates with existing system of railways and  enhances it

Data Availability
We have generated synthetic data related to railway departments, complaints data as well as customer data,as per actual data so that models give accurate outputs

Scalability
Ensuring that the databases are deployed on cloud to ensure that user load is balanced and system is scalable

Actual Project Demonstration :

Demo link : 
https://www.youtube.com/watch?v=4Ji4QcbaSEg
Implementation Images:

![image](https://github.com/user-attachments/assets/3c68c5e0-8307-4c61-8e29-33d47bbe03aa)
HOME PAGE 
This is the Home Page of our solution. 
The user is presented with a form to enter the details of the grievance. The user needs to enter his PNR, description of the grievance & image or video file for the grievance(Optional).
 Based on only these three inputs, the grievances will be categorized automatically and then smartly routed to the respective departments and officials.

![image](https://github.com/user-attachments/assets/6094b38a-df7e-4fcb-b369-8650c18e8986)

GRIEVANCE DETAILS AVAILABLE ON DEPARTMENT DASHBOARD in above image


![image](https://github.com/user-attachments/assets/6d144077-8869-4284-b60d-66d0ad1dc8a8)

DETAILED ANALYTICS BASED ON CATEGORY & PRIORITY AVAILABLE TO DEPARTMENT in above image

![image](https://github.com/user-attachments/assets/f3597a3b-b5c1-4f92-a58a-9f3e0257fbe8)
INDIVIDUAL COMPLAINT DETAILS RETRIEVAL:

![image](https://github.com/user-attachments/assets/09b3c0a9-183f-4e64-84ee-872921f7a15d)
TRAIN SPECIFIC GRIEVANCE ANALYTICS AVAILABLE TO TTE

![image](https://github.com/user-attachments/assets/f938f89c-df84-45c9-a6d2-a468b5a9d0f8)

DETAILED STEPS FOR RESOLUTION AVAILABLE TO TT

![image](https://github.com/user-attachments/assets/a9b2b338-20f5-4414-831e-2bfa17ccd9c1)
AUTOMATED NATURAL LANGUAGE BASED ROUTING TO FURTHER STATIONS

DEMO LINK:
https://www.youtube.com/watch?v=4Ji4QcbaSEg








