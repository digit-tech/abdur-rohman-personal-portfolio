# Google Sheets CMS Setup Guide

Your portfolio now supports detailed project pages! Follow this guide to set up your Google Sheets as a CMS.

## Step 1: Create Your Google Sheet

Create a new Google Sheet with the following columns (in this exact order):

| Column | Description | Required | Example |
|--------|-------------|----------|---------|
| **Slug** | URL-friendly identifier (lowercase, use hyphens) | Yes | `sales-dashboard-analysis` |
| **Title** | Project name | Yes | `Sales Dashboard Analysis` |
| **Description** | Short description (1-2 sentences) | Yes | `Built an interactive dashboard to track sales performance` |
| **Category** | Must be one of: `Data Analysis`, `Project Management`, `Engineering`, or `Product` | Yes | `Data Analysis` |
| **FullDescription** | Detailed project overview (can be multiple paragraphs) | Yes | `This project involved analyzing 3 years of sales data...` |
| **Technologies** | Comma-separated list of tools/technologies | Yes | `Python, SQL, Power BI, Excel` |
| **Challenges** | Main challenges faced | Yes | `Data quality issues required extensive cleaning...` |
| **Outcomes** | Results and impact | Yes | `Increased efficiency by 30% and saved $50K annually` |
| **ImageUrl** | URL to project screenshot/image | Optional | `https://example.com/image.jpg` |
| **Link** | External project link | Optional | `https://myproject.com` |
| **GithubLink** | GitHub repository link | Optional | `https://github.com/username/repo` |
| **Date** | Project year or date | Optional | `2024` |
| **Tags** | Comma-separated tags | Optional | `data-analysis, automation, dashboard` |

## Step 2: Fill In Your Projects

Add your projects as rows in the spreadsheet. Here's an example:

```
Slug: customer-churn-prediction
Title: Customer Churn Prediction Model
Description: Developed a machine learning model to predict customer churn with 85% accuracy
Category: Data Analysis
FullDescription: This project aimed to identify customers at risk of churning. I analyzed historical data from 50,000 customers, engineered features including purchase frequency, support tickets, and engagement metrics. The final model uses a Random Forest classifier and provides actionable insights to the retention team.
Technologies: Python, Scikit-learn, Pandas, SQL, Tableau
Challenges: Imbalanced dataset required careful sampling strategies. Feature engineering was critical to capture customer behavior patterns. Model interpretability was essential for business stakeholders.
Outcomes: Achieved 85% accuracy with 0.82 F1-score. The model now runs weekly, identifying at-risk customers. The retention team increased save rate by 25%, resulting in $200K annual revenue retention.
ImageUrl: 
Link: 
GithubLink: https://github.com/yourname/churn-prediction
Date: 2024
Tags: machine-learning, python, churn-analysis, predictive-modeling
```

## Valid Categories

Your portfolio has four main sections. Use these exact category names in your Google Sheet:

- **Data Analysis** - For data analysis, statistics, and BI projects
- **Project Management** - For project coordination, process improvement, and PM work
- **Engineering** - For technical architecture, system design, and engineering projects  
- **Product** - For product development, UX/UI, and software projects

## Step 3: Publish Your Sheet as CSV

1. In your Google Sheet, go to **File → Share → Publish to web**
2. In the dropdown, select **Comma-separated values (.csv)**
3. Click **Publish**
4. Copy the generated URL

## Step 4: Add CSV URL to Your Code

Open both files and replace the CSV URL:

**In `app/page.tsx`** (around line 31):
```typescript
const CSV_URL = "https://docs.google.com/spreadsheets/d/e/2PACX-1vQWlUHKs-sv4DLISnkrTxSZr3T4F395U8YaXPRrSfeNh1uFuLUbumEAdHvRtahGm9PgR3qvwk8Gx8Pq/pub?output=csv"
```

**In `app/project/[slug]/page.tsx`** (around line 32):
```typescript
const CSV_URL = "https://docs.google.com/spreadsheets/d/e/2PACX-1vQWlUHKs-sv4DLISnkrTxSZr3T4F395U8YaXPRrSfeNh1uFuLUbumEAdHvRtahGm9PgR3qvwk8Gx8Pq/pub?output=csv"
```

Paste your CSV URL in both places.

## Step 5: Test Your Portfolio

1. Your main portfolio page will show project cards
2. Clicking any project card or "View Details" button will navigate to the detailed project page
3. The project page displays all the comprehensive information from your Google Sheet

## Tips for Great Project Pages

- **Slug**: Use descriptive, URL-friendly slugs like `sales-dashboard`, `api-integration`, `ml-classifier`
- **Description**: Keep it concise for card display (under 150 characters)
- **FullDescription**: Tell the full story - what, why, and how (2-4 paragraphs)
- **Technologies**: List specific tools, not just categories
- **Challenges**: Be honest about difficulties - it shows problem-solving skills
- **Outcomes**: Quantify results when possible (percentages, time saved, revenue impact)
- **Images**: Use high-quality screenshots or diagrams (consider using tools like Figma for mockups)
- **Tags**: Use relevant keywords for potential search/filtering features

## Updating Content

Simply edit your Google Sheet - changes will appear automatically on your portfolio (may take a few minutes due to caching). No code changes needed!

## Example Sheet Structure

View and copy this example sheet template:
[Link to be created by user]

Or create your own following the column structure above.
