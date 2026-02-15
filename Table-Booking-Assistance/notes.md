Here’s a clean, documentation‑ready summary you can use in your portfolio. It captures the purpose, logic, and components of the automation without overwhelming technical detail.

---

# **Table Booking Bot — Automation Summary**

This n8n automation powers an AI‑assisted table‑booking chatbot for a restaurant called **Roti Bliss**. The workflow combines conversational AI, memory, and Google Sheets tools to create a smooth, automated reservation experience.

## **What the Automation Does**
- Provides a friendly chat interface where customers can request table bookings in natural language.
- Extracts key booking details: **name, date, time, and number of guests**.
- Checks for scheduling conflicts using a live Google Sheets database.
- Automatically adds new bookings when the requested time slot is available.
- Politely notifies customers when a time slot is already taken and prompts them to choose another.

## **How It Works (High-Level Flow)**
1. **Chat Trigger**  
   The workflow starts when a customer sends a message. The bot greets them and asks for booking details in any order.

2. **AI Agent (LangChain)**  
   A custom system prompt instructs the AI to:
   - Parse booking information from the conversation.
   - Use the Read Bookings Tool to check existing reservations.
   - Prevent double bookings by detecting conflicts.
   - Use the Add Bookings Tool only when the slot is free.
   - Never overwrite or cancel existing reservations.

3. **Google Gemini Chat Model**  
   Handles natural language understanding and responses.

4. **Memory Buffer**  
   Maintains short-term conversational context to keep interactions smooth and coherent.

5. **Google Sheets Tools**  
   - **Read Bookings Tool:** Retrieves all existing reservations.  
   - **Add Bookings Tool:** Appends new bookings to the sheet with structured fields (Name, Date, Time, Guest Count).

6. **Conflict Prevention Logic**  
   The AI checks for an exact match of date + time.  
   - If found → informs the customer and asks for a new time.  
   - If not found → adds the booking and confirms it.

## **Tech Stack & Integrations**
- **n8n** workflow automation
- **LangChain AI Agent**
- **Google Gemini (PaLM) model**
- **Google Sheets** (for persistent booking storage)
- **Memory buffer** for conversational continuity

## **Purpose & Value**
This automation provides a fully autonomous restaurant booking assistant that:
- Reduces manual workload
- Ensures accurate, conflict-free scheduling
- Offers a natural, human-like customer experience
- Keeps all booking data organized in a central Google Sheet

---

If you'd like, I can also format this as:
- A portfolio case study  
- A LinkedIn project description  
- A GitHub README  
- A short marketing-style blurb  

Just tell me the style you want.
