
# ReMindMe System Architecture

## Overview

**ReMindMe** is engineered to function like a discreet, highly efficient personal assistant.  
The system uses a **microservices approach** to separate message handling, intelligent parsing, and persistent scheduling.  

This design ensures the service is **lightweight**, **highly scalable**, and **privacy-focused**.



## Components in Detail

### 1. Chatbot Interface (_The Listener_)
**Purpose:**  
User-facing component that receives input and delivers output.

**Implementation:**  
WhatsApp / Telegram Bot APIs

**Responsibilities:**
- Securely receive and validate all incoming messages  
- Send reminder notifications and simple command responses  


### 2. Backend Server (_The Conductor_)
**Implementation:**  
Node.js + Express

**Responsibilities:**
- Orchestrates data flow between components  
- Handles API calls  
- Serializes raw message text into a structured database object  



### 3. AI/ML Layer (_The Brain_)
**Implementation:**  
Python NLP Service (spaCy or HuggingFace)

**Responsibilities:**
- Performs **Commitment Detection**  
- Extracts key entities: **Task** and **Temporal Trigger**  
- Returns a structured JSON output  



### 4. Database (_The Memory_)
**Implementation:**  
MongoDB

**Responsibilities:**
- Provides persistent storage of scheduled reminders  
- Optimized for fast querying by the Scheduler  



### 5. Scheduler (_The Timekeeper_)
**Implementation:**  
Cron jobs or serverless functions

**Responsibilities:**
- Polls MongoDB for imminent reminders  
- Triggers the notification process via the Backend Server  


##  Technical Feasibility & Trust

ReMindMe is built on **mature, publicly available technologies** 
such as Bot APIs, Node.js, MongoDB, and modern NLP frameworks like spaCy or HuggingFace.

The **AI/ML Layer** provides the greatest value by accurately detecting nuanced conversational intent.  
**Privacy** is a core principle — messages are processed and deleted quickly,  
ensuring a **trustworthy and secure** user experience.

Link to Dataflow: https://miro.com/app/board/uXjVJttwZ0I=/

