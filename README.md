# ESG Report Automation - UiPath Project

## Project Overview

This project automates the ESG (Environmental, Social, and Governance) compliance process for IT companies using UiPath. It enables authorities to upload ESG data in various formats (Excel, PDF, CSV), validates the data against dynamic rules, and generates automated reports, summaries, and dashboards — all integrated with AI and cloud technologies.

No hardcoding. No manual work. 100% dynamic and scalable.

---

## Features & Components

### 1. File Upload Page (UiPath Apps)

* **Controls:**

  * Uploads Excel, PDF files
  * Upload button triggers bot
  * Status label shows real-time success/error
  * Optional table shows last 3 uploads

* **Automation:**

  * Saves file to `Input/`
  * Triggers `main.xaml`
  * Bot processes and stores results automatically

### 2. Bot Logic (`main.xaml` - UiPath Studio)

* **Steps:**

  1. Get file path from App
  2. Detect file type (.xlsx, .pdf, etc.)
  3. Extract fields dynamically
  4. Load validation rules using OpenAI
  5. Loop through data and validate
  6. Score the file (pass %)
  7. Call OpenAI for AI summary
  8. Generate report 
  9. Save results in excel form
  10. Output: status, PDF path, score, summary

### 3. Dashboard Page (UiPath Apps)

* **Dynamic data display**

  * Columns: FileName, Score, Status, Violations, Date, Download Link
* **Filters:**

  * Score range (e.g. >80%)
  * Date Range

### 4. 🧠 Chatbot Page (UiPath Apps + OpenAi)

* **User Input:**

  * Text box + Ask button
* **Backend:**

  1. Reads latest file entry from Excel
  2. Builds a prompt from extracted ESG data
  3. Sends prompt to GPT-4
  4. Returns and displays response

### 5. 📄 Auto-filled ESG Report (Word Template)

* Template: `ESG_Report_Template.docx`
* Placeholders:

  * Company: <<Company>>
  * Date: <<Date>>
  * Score: <<Score>>%
  * Violations: <<Violations>>
  * AI Summary: <<AISummary>>
* Generates PDF and saves to `Output/`

---

## Tools & Technologies Used

| Tool          | Use                                   |
| ------------- | ------------------------------------- |
| UiPath Apps   | Upload, Dashboard, Chatbot UI         |
| UiPath Studio | Automation bots                       |
| Orchestrator  | Bot trigger from Apps                 |
| Google Sheets | Dynamic, live database                |
| Word          | Auto-filled report generation         |
| OpenAI API    | Generate AI summary and chat response |

---

## Project Folder Structure

```
/ESG_Automation
  /Input                ← All uploaded files
  /Output               ← All generated reports
  /Templates
      ESG_Report_Template.docx
  main.xaml
```

---

## ✅ Final Output for Judges

| Section     | Description                                             |
| ----------- | ------------------------------------------------------- |
| Upload Page | Upload any ESG Excel or PDF files                       |
| Backend     | Auto-validates using AI                                 |
| Report      | AI-powered summary & violation analysis in PDF format   |
| Dashboard   | Real-time dashboard with filters                        |
| Chatbot     | Real-time ESG Q\&A using OpenAI + latest uploaded data  |
| E-mail      | Sends the reports as E-mail to the Authorities          |

---

## Authors

[JesliPriya](https://github.com/jeslipriya), [Akash](https://github.com/Akashmathiyalagan), [Mridula](https://github.com/MRIDULA-0-9)
