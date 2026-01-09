# daily-market-digest-automation
Built a scheduled Power Automate workflow that aggregates real-time stock prices and curated financial news into a daily email digest. The automation delivers a structured market summary for three equities (MSFT, TSLA, NVDA) using external financial and news APIs, and sends the report via Outlook email each morning.

## Tech Stack
- Microsoft Power Automate
- Alpha Vantage API (Market Data)
- NewsAPI (Financial News)
- Outlook Email Connector

## 1. Stock Market Summary

Involved Actions:
- Scheduled recurrence trigger to run the workflow daily at a fixed time
- Iterative processing over a predefined list of equity symbols (MSFT, TSLA, NVDA)
- HTTP integration with Alpha Vantage API to retrieve real-time global quote data
- Rate-limit handling via controlled delay between API calls (Alpha Vantage API dooesn't allow consecutive API calls)
- JSON parsing and field extraction for price and daily percentage change
- HTML generation using string variables to construct a formatted price snapshot

<img width="643" height="573" alt="Screenshot 2026-01-09 at 5 47 53 AM" src="https://github.com/user-attachments/assets/cc82a299-ac3a-4533-b59f-22c6ba615b90" />





## 2. News Report

Involved Actions:
- Iterative query generation per company using search terms
- HTTP integration with NewsAPI to retrieve the most recent relevant headlines
- Conditional filtering to ensure company-specific relevance
- Structured parsing of article titles and URLs
- Assembly of a clean, readable news section per company

<img width="643" height="572" alt="Screenshot 2026-01-09 at 5 48 29 AM" src="https://github.com/user-attachments/assets/3d9329e2-9a79-496a-a3ec-615f634e88e9" />



## 3. Sample Email Report

At 7:30am each morning, the workflow automatically delivers the following market summary email.
<img width="634" height="588" alt="Screenshot 2026-01-09 at 5 49 32 AM" src="https://github.com/user-attachments/assets/e02aa962-393f-4984-a9f1-7a4b9ba2fdc2" />



## 4. Automation Efficiency

This scheduled automation executes 15+ actions per run, integrates 2 external APIs, and performs 6 HTTP requests per execution. The recorded average runtime of this workflow is 9 seconds.

<img width="687" height="410" alt="Screenshot 2026-01-09 at 11 43 18 AM" src="https://github.com/user-attachments/assets/ac2717d7-ed62-4c47-a669-4ddfb93c6ce9" />


