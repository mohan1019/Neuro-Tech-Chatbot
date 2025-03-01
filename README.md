# **LLM-Powered Chatbot for Document Querying and Database Interaction**

A project developed in collaboration with **NeuroTechR3**, designed to integrate an **AI-driven chatbot** to assist users in querying documents and retrieving personalized data from a **NoSQL database**. This chatbot is part of the **R3THA neurorehabilitation platform**, aiding users in their rehabilitation journey by **automating responses, troubleshooting setup issues, and retrieving progress metrics** dynamically.

## ** Project Overview**
### **Objective**
The primary goal of this project is to develop an **intelligent chatbot** that can handle:
- **Document-based queries** (FAQs, manuals, troubleshooting)
- **User-specific database queries** (fetching rehabilitation progress data)
- **Graphical representation** of progress data (automated graph generation)
- **Secure API access** for seamless integration with R3THA

### **Key Challenges Addressed**
✅ Reducing **manual support overhead** by automating FAQs  
✅ Improving **user engagement** with an interactive chatbot  
✅ Enabling **real-time retrieval of rehabilitation data**  
✅ Providing **visual insights** through dynamically generated graphs  
✅ Ensuring **scalability and security** using cloud-based deployment  

---

## ** Tech Stack**
| Component | Technology Used |
|-----------|----------------|
| **Backend** | Flask (Python), OpenAI API, LangChain |
| **Frontend** | React, Deep-Chat-React |
| **Database** | MongoDB Atlas (NoSQL) |
| **Vector Storage** | Pinecone (Vector DB for RAG) |
| **Hosting** | AWS EC2, S3, RDS |
| **APIs** | RESTful APIs (Flask) |
| **Graphing** | Matplotlib (Dynamic Graphing) |

---

## ** Project Architecture**
### **System Workflow**
1. **User Query Processing**
   - Users interact with the chatbot through a frontend interface.
   - The chatbot processes the query using an **LLM-powered contextualizer** to maintain conversation flow.

2. **Query Classification**
   - The system determines whether the query is a **document-based query** (RAG) or a **database query** (NoSQL retrieval).

3. **Data Retrieval & Processing**
   - If document-based, the system retrieves relevant content using **Pinecone Vector DB**.
   - If database-based, it converts the query into a **MongoDB aggregation query** using a custom-built **NoSQL agent**.

4. **Response Generation**
   - The chatbot returns a **text response** or a **graph (if required)** using **Matplotlib**.

5. **Final Output**
   - The response is displayed in the chatbot interface.

### **Architecture Diagram**
_(Insert architecture_diagram.png here)_

---

## ** Data Flow**
### **1️⃣ Query Routing Mechanism**
- The **NoSQL vs RAG Classifier** determines whether the query should be handled by the **Knowledge Base (RAG)** or **Database (MongoDB)**.

### **2️⃣ RAG-Based Document Retrieval**
- Documents (FAQs, manuals) are stored in **Pinecone Vector DB**.
- When queried, relevant document chunks are **retrieved and processed using GPT-4o**.

### **3️⃣ NoSQL Query Execution**
- User-specific queries are **converted into MongoDB queries**.
- Retrieved data is either **displayed as text** or **visualized as a graph**.

### **Data Flow Diagram**
_(Insert data_flow_diagram.png here)_

---

## ** Screenshots**
### **1️⃣ Chatbot UI**  
_(Insert home_page_ui.png)_

### **2️⃣ Expanded Chatbot View**  
_(Insert chatbot_expanded.png)_

### **3️⃣ Graph Generated from Database Query**  
_(Insert db_query_visualization.png)_

### **4️⃣ Admin Upload Page**  
_(Insert upload_page.png)_

### **5️⃣ API Response (Postman)**  
_(Insert api_response_postman.png)_

---

## **🔌 API Documentation**
### **1️⃣ Chatbot API**
- **Endpoint:** `/llm/query/`
- **Method:** `POST`
- **Request Format:**
  ```json
  {
    "message": "How do I set up my Ultraleap device?"
  }
  ```
- **Response Format:**
  ```json
  {
    "output": "To set up your Ultraleap device, follow these steps..."
  }
  ```

### **2️⃣ User Login API**
- **Endpoint:** `/llm/login/`
- **Method:** `POST`
- **Request Format:**
  ```json
  {
    "username": "user1",
    "password": "password123"
  }
  ```
- **Response Format:**
  ```json
  {
    "status": "success",
    "message": "User logged in successfully"
  }
  ```

### **3️⃣ File Upload API (Admin Only)**
- **Endpoint:** `/llm/upload/`
- **Method:** `POST`
- **Request Format:** (Use form-data to upload a PDF)
- **Response Format:**
  ```json
  {
    "message": "File uploaded successfully"
  }
  ```

---

## **🧪 Testing & Evaluation**
### **1️⃣ Verification Strategies**
- **Manual Testing:** Predefined user queries were tested.
- **LangSmith Logs:** Used to validate LLM responses.
- **Database Query Validation:** Cross-checked responses against expected values.

### **2️⃣ Accuracy Checks**
- Verified chatbot responses with **actual database values**.
- Ensured **graph responses** matched expected patterns.

### **3️⃣ Security Measures**
✅ **Flask API secured with HTTPS**  
✅ **Role-based access for admins**  
✅ **Authentication for user-specific queries**  

---

## ** Lessons Learned**
- **Handling LLM Hallucinations**: Implemented **prompt engineering & response verification**.
- **Scaling RAG for large documents**: Optimized **chunking & metadata retrieval**.
- **Deployment Challenges**: Used **process managers (PM2) on AWS EC2**.

---

## ** References**
- **NeuroTechR3 Official Documentation**
- **LangChain Docs** - [LangChain](https://python.langchain.com/)
- **OpenAI API** - [OpenAI](https://platform.openai.com/)
- **MongoDB Aggregation Framework** - [MongoDB Docs](https://www.mongodb.com/docs/manual/aggregation/)

---

## ** Contributors**
- **Jason Cho** (Project Manager & Developer)  
- **Monil Shah** (Generative AI Developer)  
- **Mohan Kumar Garaga Malleshappa** (Database & Backend Developer)  
- **Saketh Puramsetti** (Frontend Developer & AWS Deployment)  

---

## ** Conclusion**
This **LLM-powered chatbot** successfully integrates **document querying, NoSQL interaction, and AI-powered graphing**, making R3THA’s rehabilitation process **simpler and more efficient** for users. 🚀

