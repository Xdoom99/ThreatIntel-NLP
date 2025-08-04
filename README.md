# Project Title: ThreatIntel-NLP, A cyber threat intelligence Pipeline using NERs and LLMs

# Goal: To automatically extract important information like organization, people, locations, date, IP Address, Indicators Of Compromise (IOCs) such as IP addresses, domains, CVEs, hashes,etc from real world cybersec articles and reports. After then summarize them into clean markdown reports for threat analysis or security operation centres (SOCS)

# My Core Idea that i have used here are below
1. NLP Technique which is NER (Name Entity Recognition)
2. Custom threat-focused rules
3. OpenAI GPT models for summarization to build lightweight automated pipeline for CTI (Cyber Threat Intelligence)

# Tools and Libraries
spaCy->	Extracts standard entities (like ORG, DATE, GPE, etc.)
regex-> Matches custom threat entities like IPs, CVEs, hashes
newspaper3k-> Scrapes full articles from threat URLs
OpenAI-> Summarizes the articles using GPT-4 (or GPT-3.5)
Markdown-> Saves reports in clean, readable format
Colab-> Entire pipeline runs dynamically in the cloud

# Pipeline Breakdown
# 1. Input Source: The project starts with a list of cybersecurity news articles  e.g., from ThreatPost.
# 2. Article Scrapping: Each article URL is passed to newspaper3k, which: Downloads the webpage Cleans the HTML Extracts the raw article text and title
# 3. Name Entity Recognition: SpaCy extracts standard entities: e.g., ORG, PERSON, DATE, GPE, MONEY, etc. You also apply custom rules using regular expressions: IP_ADDRESS: IPv4/IPv6 pattern match, DOMAIN: Regex for common TLDs, CVE: e.g., CVE-2024-1234, HASH: SHA256 or MD5 patterns, This combination allows you to extract both linguistic entities and cybersecurity-specific ones.
# 4. Summary Generation: The raw article text is sent to OpenAI’s GPT-4 (or GPT-3.5) via API. It returns a concise summary, extracting key findings or breach impacts
# 5. Report Generation: All extracted data is compiled into a Markdown report: Title + Source link, Extracted entities, grouped by type, GPT-based auto-summary
# /MyDrive/CyberNERReports/ in Google Drive, perfect for: 📁 Sharing with CTI teams, 📄 Uploading to GitHub, 🧾 Building a searchable report database

# Output Example 
# Student Loan Breach Exposes 2.5M Records

🔗 [Source Link](https://threatpost.com/student-loan-breach-exposes-2-5m-records/180492)

 Extracted Entities

**ORG**: Nelnet Servicing, OSLA, EdFinancial  
**PERSON**: Bill Munn, Biden  
**DATE**: July 21, 2022, August 17, 2022  
**MONEY**: 10,000, up to $1 million  
...

 Auto Summary
2.5 million people were affected by the breach. Names, emails, and SSNs were exposed. The breach was discovered on August 17th.


# Further Idea: Add PDF integration, Use RAG pipelining, Integrate it with dashboard (streamlit)




