# Meesho_Analysis
why people does not want to use meesho aap
Customer Feedback Analysis and Automated Response
Overview

This project automates the analysis of customer feedback collected from the Meesho shopping application. The objective is to identify critical customer reviews using rule-based filtering and generate personalized apology emails using a Generative AI model.

The project is implemented using Python, Pandas, and LangChain with a Large Language Model (LLM).

Dataset
Dataset Source: Kaggle
Dataset Used: Meesho Customer Reviews Dataset
Format: CSV

The dataset contains customer reviews, star ratings, review dates, likes, and company replies.

Important columns used in this project:

Review – Customer review text
Rating – Customer rating (1–5 stars)
Data Cleaning Approach

The following preprocessing steps were performed:

Loaded the dataset using Pandas.
Checked dataset information using df.info().
Identified missing values using df.isnull().sum().
Removed unnecessary columns not required for the analysis.
Renamed:
content → Review
score → Rating
Converted all review text to lowercase.
Removed special characters, punctuation, numbers, and extra spaces using Regular Expressions.
Verified that the cleaned dataset was ready for further analysis.
Rule-Based Logic

Instead of using Machine Learning, simple Python logic was used.

Critical Reviews

A review is considered Critical if:

Rating = 1
Rating = 2

Example:

critical_reviews = df[df["Rating"] <= 2]
Complaint Keyword Extraction

The project extracts frequently occurring complaint words from critical reviews using:

Python string operations
collections.Counter

Common stopwords were removed before counting.

Example complaint keywords include:

worst
delivery
refund
return
service
bad
experience
Generative AI

LangChain was used to connect to a Generative AI model.

The model receives the cleaned customer review as input and generates:

A personalized apology email
Professional tone
Empathetic response
Issue acknowledgement
Assurance of investigation
Customer support contact suggestion
Project Workflow
Load Dataset
Clean Data
Handle Missing Values
Rename Required Columns
Filter Critical Reviews (1 & 2 Star)
Extract Complaint Keywords
Select Top 3 Critical Reviews
Generate AI-based Apology Emails
Technologies Used
Python
Pandas
Regular Expressions (re)
Collections.Counter
LangChain
Google Gemini API / Groq API
Jupyter Notebook
How to Run the Project
Step 1

Install required libraries:

pip install pandas langchain langchain-core langchain-google-genai langchain-community langchain-groq
Step 2

Download the Kaggle dataset and place the CSV file in the project folder.

Step 3

Open the Jupyter Notebook:

Customer_Feedback.ipynb
Step 4

Run all notebook cells in sequence.

API Key Configuration

This project requires an LLM API key.

Option 1: Google Gemini
import os

os.environ["GOOGLE_API_KEY"] = "YOUR_GOOGLE_API_KEY"
Option 2: Groq
import os

os.environ["GROQ_API_KEY"] = "YOUR_GROQ_API_KEY"

Replace "YOUR_GOOGLE_API_KEY" or "YOUR_GROQ_API_KEY" with your own API key before running the notebook.

Output

The notebook generates:

Cleaned customer review dataset
Critical reviews (1–2 stars)
Most common complaint keywords
Three AI-generated personalized apology emails
