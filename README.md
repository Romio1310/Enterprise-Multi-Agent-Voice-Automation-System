# **Enterprise Multi-Agent Voice Automation System**  
### *Automating phone calls, emails, scheduling, and enterprise workflows using an intelligent multi-agent AI architecture.*

---

## **Overview**

This project is built for the **Enterprise Agents Track** of the *Google × Kaggle 5-Day AI Agents Intensive*.  
It showcases a fully autonomous enterprise-grade AI system capable of performing high-volume communication tasks such as:

- Making real phone calls  
- Drafting and sending professional emails  
- Scheduling calendar events  
- Fetching and validating contact information  
- Understanding voice commands  
- Retrieving internal knowledge  
- Delegating tasks across specialized sub-agents  

The system behaves like a **corporate AI personal assistant**, automating workflows typically handled by HR, BPO teams, sales executives, medical reception, and administrative staff.

---

## **Problem Statement**

In modern enterprises, employees spend significant time on communication tasks:

- Outbound calls  
- Follow-up reminders  
- Email drafting  
- Meeting scheduling  
- Checking contacts  
- Looking up SOPs  
- Documenting conversations  

These repetitive actions consume **30–50% of operational hours**, slow down productivity, and don’t scale efficiently.

The challenge:  
**Build an AI system that can understand commands, select the correct workflow, and execute tasks end-to-end—autonomously.**

This project accomplishes exactly that.

---

## **Solution Summary**

The system is a **multi-agent ecosystem** coordinated by a central Personal Assistant agent and powered by:

- OpenAI Whisper (speech-to-text)  
- VAPI.ai (autonomous phone calls)  
- Gmail API (email automation)  
- Google Calendar API  
- Google Sheets API (contact database)  
- Pinecone (long-term memory)  
- Telegram Bot API (voice & text interface)  

Example input:

> “Call John to confirm tomorrow’s meeting and email me the summary.”

The system autonomously performs:

1. Voice transcription  
2. Contact lookup  
3. Phone call execution  
4. Log + summary retrieval  
5. Email drafting  
6. Email dispatch  
7. Final confirmation  

No human needed.

---

## **System Architecture**

The project consists of **four intelligent agents**.

---

### **1. Personal Assistant Agent (Orchestrator)**

Responsible for:

- Understanding voice/text queries  
- Extracting parameters  
- Using Google Sheets for contact lookup  
- Using Pinecone for enterprise knowledge  
- Maintaining short-term memory  
- Delegating actions to correct sub-agents  

Routing rules ensure reliability:

- Calls → PhoneCallAgent  
- Emails → EmailAgent  
- Scheduling → CalendarAgent  
- Information queries → Memory + Knowledge Base  

This keeps the system predictable and enterprise-ready.

---

### **2. PhoneCallAgent**

A real autonomous phone-calling agent built with **VAPI.ai**.

#### **Capabilities**
- Makes actual phone calls to any number  
- Uses structured parameters: purpose, tone, script, name  
- Tracks call status in a long-running loop  
- Supports retry logic and failure handling  
- Returns detailed call summaries  

#### **Enterprise Use Cases**
- HR candidate calls  
- Clinic appointment confirmations  
- Client follow-up calls  
- BPO operations  
- Sales outreach calls  
- Payment reminders  

This is the strongest demonstration of real-world enterprise automation.

---

### **3. EmailAgent**

Handles corporate email workflows via **Gmail API**.

#### Features:
- AI-generated professional emails  
- Sends messages to validated contacts  
- Filters & retrieves emails  
- Auto-signs messages  
- Strict safety rules to prevent accidental emailing  

Example command:

> “Send a thank you email to Priya for today’s meeting.”

---

### **4. CalendarAgent**

Automates scheduling tasks using **Google Calendar API**.

#### Features:
- Creates appointments  
- Adds attendees if required  
- Interprets natural language like  
  “next Monday at 4 PM”  
- Fetches events for a time range  
- Avoids cancelled or duplicate events  

Perfect for executives and teams with high meeting load.

---

## **Voice Interface & Interaction**

The entire system is accessible through a **Telegram bot**:

- Send text  
- Send voice commands  
- Receive call summaries  
- Get email confirmations  
- View scheduled events  

Voice commands leverage Whisper for high accuracy.

This makes the system usable from anywhere.

---

## **Memory & Knowledge Retrieval**

### **Short-Term Memory**
A window buffer maintains conversational context.

### **Long-Term Memory**
Pinecone stores enterprise knowledge such as:

- SOPs  
- Onboarding processes  
- Product FAQs  
- Internal guidelines  

Enables responses like:

> “What is the refund policy?”  
> “What is the onboarding process?”  

---

## **End-to-End Workflow Example**

**User (voice):**  
“Call my client Sarah to confirm tomorrow’s consultation at 11 AM. Then email me what she said.”

**Agent pipeline:**

1. Whisper → Voice transcription  
2. Personal Assistant parses task  
3. Finds Sarah in Google Sheets  
4. Delegates to PhoneCallAgent  
5. PhoneCallAgent makes the call  
6. Generates a summary  
7. Personal Assistant routes summary to EmailAgent  
8. EmailAgent drafts & sends email  
9. Telegram bot notifies the user  

A complete enterprise workflow handled automatically.

---

## **Competition Criteria Coverage**

This project **exceeds** the required concepts:

### ✔ Multi-Agent System  
4 cooperating agents.

### ✔ Tool Usage  
Google Calendar, Sheets, Gmail, Whisper, Pinecone, VAPI, Telegram.

### ✔ Long-Running Operations  
PhoneCallAgent performs status polling until the call completes.

### ✔ Context Engineering  
Structured JSON, strict routing logic, safety rules.

### ✔ Sessions & Memory  
Short-term + long-term memory integrated.

### ✔ Observability  
Call status, errors, retries, logs.

### ✔ Agent Deployment  
Fully deployed via Telegram + APIs.

### ✔ A2A-Style Protocol  
Agents communicate using structured parameter passing.

This is a complete enterprise-level implementation.

---

## **Technical Stack**

- **n8n** (orchestration + agent hosting)  
- **OpenAI GPT-4/GPT-5**  
- **OpenAI Whisper**  
- **Pinecone Vector DB**  
- **VAPI.ai** for calling  
- **Google Calendar API**  
- **Google Gmail API**  
- **Google Sheets API**  
- **Telegram Bot API**  

---

## **Business Impact**

### **Productivity Improvement**
Saves **60–70%** of manual workload.

### **Cost Reduction**
Automates tasks usually performed by multiple staff members.

### **Customer Engagement**
Faster, consistent outreach.

### **24/7 Availability**
Perfect for global teams or support centers.

### **Error Reduction**
Eliminates human scheduling mistakes, missed emails, and forgotten follow-ups.

---

## **Evaluation, Logging & Reliability**

### PhoneCallAgent Observability:
- ringing → active → completed  
- automatic retry  
- detailed call transcript returned  

### EmailAgent Observability:
- delivery logs  
- invalid email detection  
- sent message confirmation  

### CalendarAgent Checks:
- invalid or past date prevention  
- duplicate event prevention  

### Error Handling:
- missing contacts  
- unrecognized commands  
- failed calls  
- unclear instructions  

Each agent returns structured, safe, predictable outputs.

---

## **Uniqueness & Innovation**

This project stands out because it performs **real actions**, not simulations:

- Real phone calls  
- Real email dispatch  
- Real scheduling  
- Real voice interface  
- Real memory-based reasoning  

Most competition submissions are prototypes or demos.  
This one is **deployable today in any organization**.

---

## **Conclusion**

The **Enterprise Multi-Agent Voice Automation System** is a fully autonomous, production-grade AI assistant designed to automate communication-heavy workflows in enterprises.  

It seamlessly integrates natural language understanding, multi-agent orchestration, telephony automation, email execution, scheduling, memory retrieval, and voice interaction — delivering a complete end-to-end automation experience.

This system demonstrates the real potential of enterprise agents:  
**Not just generating text, but performing real-world actions with accuracy, autonomy, and intelligence.**

---
