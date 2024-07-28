# AI Student Assistant

## Objective
The purpose of this project is to develop an AI chatbot that assists students with course material, including summarizing lectures, exams preparation questions and general Q&A. The chatbot will provide a user-friendly interface for students to engage with and better understand the content of their courses.

## Main Flow for application
  
1. **User access the chat through the designated communication channel from the web app**
2. **User create account or sign-in**
3. **User inputs question in the chat interface**
4. **The server receives the user prompt and uses Azure OpenAI service to process and understand the query**
5. **The server use indexes from raw data to customize generative AI responses and uses the OpenAI service to create an answer**
6. **The web app presents the response to user**

## Architectural diagram

![Moodle - AI Search Engine (1)](https://github.com/user-attachments/assets/48a15a0a-dfa7-40b0-952c-1dff31e01143)
  
## Components

1. **Blob Storage**
   - Service for storing large amounts of unstructured data, serve as the repository for all course materials. Currently "Advanced Python" (.py files) and "Computer Organization and Assembly Language" (.txt and .pdf files) will be manually uploaded.

2. **Azure AI Studio**
   - The LLM (Large Language Model) will be deployed through Azure AI Studio. This platform enable API endpoint for AI models. For this MVP (Minimum viable product), GPT-4o model will be used.
   - Azure Search service is a part of Azure AI Studio. It provides indexing and querying capabilities for data stored in Azure. It will be used to create indexes of the course material, making it easier to search and retrieve relevant information quickly.

3. **Microsoft Entra**
   - Users authentication service for the web app. Allowed autentication ways: Entra, Facebook, Google, X.

4. **Azure App Service**
   - Students will interact with the chatbot through a web application built using the Python Django framework. The application will be hosted on Azure App Service, which is a fully managed platform for building, deploying, and scaling web apps.
  
5. **Azure CosmosDB**
   - Azure Cosmos DB is NoSQL database solution. It will store chat history and list of available courses for each user.

## Use Cases

1. **Lecture Summarization**
   - Students can ask the chatbot to summarize specific lectures or topics, providing concise overviews of the material covered.

2. **Exam Preparation**
   - The chatbot can assist students in preparing for exams by:
     - Generating sample questions based on the course material.
     - Providing detailed explanations of complex concepts.
     - Offering tips and strategies for effective study practices.

3. **Interactive Q&A**
   - Students can ask questions about the course material, and the chatbot will retrieve relevant information from the indexed documents to provide accurate answers.

## Conclusion
This project aims to enhance the learning experience by leveraging cutting-edge AI technology and cloud services. By providing an interactive and intelligent chatbot, students will have a valuable tool to help them navigate and master their course material more effectively.

## Future Steps
1. **Automatic retriving of course data from Moodle**
2. **Claude AI model will allow to interact with Hebrew course materail**
