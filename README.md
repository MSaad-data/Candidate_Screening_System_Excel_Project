# Candidate_Screening_System_Excel_Project
An Excel-based Candidate Screening System with a full dataset, automated skill-requirement checks, salary filtering, and final shortlisting logic. Includes summary metrics and multiple pivot-table visuals like shortlist analysis, role-wise applicant insights, and salary comparisons to support hiring decisions.
## Dataset used
 <a href="https://github.com/MSaad-data/Candidate_Screening_System_Excel_Project/blob/main/Candidate_Screening_System.xlsx">Dataset view</a>
A US-based company opened hiring for four roles: Data Analyst, Business Analyst, Marketing Analyst, and Operations Coordinator.
The recruiter shared the job posts online. After 15 days, many people applied. The recruiter did an initial screening and selected 25 candidates for the next review round.
To manage these candidates, the recruiter collected their details in an Excel file.
This Excel sheet became the main dataset for the project.
### These were the raw columns in the file:
Candidate_ID

Candidate_Name

Gender

Applied_Role

Excel_Experience (Years)

SQL_Experience (Years)

Python_Experience (Years)

Expected_Salary ($)

Availability

Recruiter_Score

Candidate_City

The goal of this project was to help the recruiter understand the candidates better, check their skills, compare salaries, and make faster hiring decisions using Excel.

## Adding Logic Columns for Smarter Screening
After loading all 25 candidates, the next step was to help the recruiter quickly see who meets the job requirements.
For this, I created several new columns using simple IF conditions and AND logic in Excel.

### These new columns were:
Meets_Excel_Requirement

Meets_SQL_Requirement

Meets_Python_Requirement

Meets_All_Requirements

Salary_Within_Budget

Final_Shortlisted

These columns act like automatic checks.
Instead of the recruiter reading each row one by one, Excel instantly tells:

Who has enough experience

Who fits within the salary budget

Who meets all requirements together

Who should be shortlisted

### The Target Requirements Used
We used 3 years of experience as the minimum target for Excel, SQL, and Python.
We also set the salary budget limit to $55,000.

### Example logic:
If a candidate has 3+ years of Excel, then the Excel requirement = TRUE

If their expected salary ≤ 55,000, salary is within budget

If the candidate meets all three skill requirements AND fits the budget, then they become Final_Shortlisted = TRUE

Fully Adjustable for the Recruiter

The great thing about this setup is that everything is easy to change.

### If the recruiter wants:
4+ years in SQL

2+ years in Python

A salary budget of $60,000

They can simply edit the numbers in the formula, and Excel will instantly update all results.
This makes the system flexible, simple, and reusable for future hiring rounds.

## Building a Simple Summary to Help the Recruiter
Once all logic columns were ready, I created a Summary Analysis section.
The goal was to give the recruiter a quick snapshot of the entire candidate pool without looking through every row.
### Here is what the summary shows:
<img width="390" height="121" alt="image" src="https://github.com/user-attachments/assets/6a6c5754-ae44-47c1-9296-a17bef5f4eec" />

### Why did we build this summary?
A recruiter usually wants answers to simple questions like:

How many people applied?

How many actually qualified?

What salaries are candidates expecting?

Are shortlisted candidates asking for reasonable salaries?

What is the quality (recruiter score) of the shortlisted group?

Instead of checking row by row, this small summary gives the recruiter a big-picture view in seconds.

It helps the recruiter answer:
👉 “Do we have enough good candidates or do we need to reopen the job posting?”

### Formulas Used

To build this summary, I used basic Excel functions:

**Total Candidates:**
=COUNTA(A2:A26)

**Total Shortlisted:**
=COUNTIF(Q2:Q26, TRUE)

**Total Not Shortlisted:**
=COUNTIF(Q2:Q26, FALSE)

**Average Expected Salary:**
=AVERAGE(H2:H26)

**Average Salary of Shortlisted:**
=AVERAGEIF(Q2:Q26, TRUE, H2:H26)

**Average Recruiter Score of Shortlisted:**
=AVERAGEIF(Q2:Q26, TRUE, J2:J26)

At this point, the recruiter now has:
Clean data
Logic-based evaluations
A clear summary of results
Now the next step was to add visuals and pivot tables so the recruiter can see patterns even more clearly.

## Visual 1: Shortlisted vs Not Shortlisted (Pie Chart)
After building the summary, I created the first visual: a pie chart that compares Shortlisted vs Not Shortlisted candidates.
This chart quickly shows how many people actually met all the requirements.
Out of 25 candidates:

4 candidates (16%) are fully shortlisted

21 candidates (84%) are not shortlisted

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f062c7a2-2a5b-435e-9e81-d1fd7975c03b" />
A recruiter needs to see the overall quality of the applicant pool at a glance.

Instead of reading numbers or scanning a table, the pie chart gives a quick visual snapshot.
It helps answer simple but important questions:

“Do we have enough qualified candidates?”

“Did most people fail because of skills or salary?”

“Should we keep interviewing or reopen the job posting?”

Since only 16% of candidates are shortlisted, the recruiter can understand that:

Most applicants did not meet skill requirements or Their salary expectations were too high

**This visual helps the recruiter decide if they should:**

Adjust the job post

Increase the salary budget

Focus on skill development programs

Or start a new hiring round

This makes the hiring process faster and more informed.

## Visual 2: Applications by Role vs Final Shortlisted (Clustered Column Chart)

The second visual is a clustered column chart showing how many candidates applied for each role and how many were finally shortlisted.
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4c3a182e-df13-4acf-b1f5-5c8cbe651c3d" />


### What the chart shows

Business Analyst: 7 applications → 2 shortlisted

Data Analyst: 6 applications → 0 shortlisted

Marketing Analyst: 5 applications → 1 shortlisted

Ops Coordinator: 7 applications → 1 shortlisted

A recruiter needs to see the quality of applicants for each role.
This chart shows both quantity and quality, so the recruiter can quickly identify:

Roles with many applications but few qualified candidates

Roles where most applicants meet requirements

Talent gaps in certain roles

### From this chart:
**Business Analyst:** Most applications are strong; focus interviews here.
**Data Analyst: **No candidates fully meet requirements; consider re-opening the role or adjusting expectations.
**Marketing Analyst & Ops Coordinator: **Only 1 candidate each meets all criteria; recruiter may need additional sourcing.
This visual helps the recruiter prioritize interview efforts and make data-driven hiring decisions, saving time and improving outcomes

## Visual 3: Expected Salary vs Shortlisted Status (Clustered Column Chart)

**Not Shortlisted:** Average salary = $54,286

**Shortlisted:** Average salary = $50,000

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/80242720-7548-4669-ba51-22485c46df1e" />

When hiring, budget is very important. This chart shows that most candidates who meet all requirements are within the budget, while higher salaries often belong to candidates who don’t fully meet skill or budget criteria.
From this, the recruiter can focus on candidates who are fully qualified and affordable, making the hiring process faster and cost-effective.

## Visual 4: Average Skill Experience by Role (Clustered Bar Chart)
This chart shows the average Excel, SQL, and Python experience of candidates for each role.

**Business Analyst:** Balanced skills, strong SQL and Python

**Data Analyst: **Strong SQL and Python, well-aligned with role

**Marketing Analyst:** High Python, good analytics skills

**Ops Coordinator: **Lowest technical experience, fits role nature

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7ad854cd-c6f6-4859-8707-c04b391c3bec" />

Recruiters can quickly see if candidates’ skills match role expectations and focus on roles with the strongest fit.

## Summary & Recommendations
This project shows how Excel can help recruiters make data-driven hiring decisions.

**From the analysis, we see:**
Only 16% of candidates met all requirements and budget.
Some roles, like Business Analyst, have strong applicants, while roles like Data Analyst need more sourcing.
Candidates who meet requirements usually stay within the salary budget, helping control hiring costs.
Skill gaps are clear, so recruiters can plan training or adjust role expectations.

### How this helps recruiters
Quickly shortlist candidates based on skills, experience, and salary.
Compare roles to see where talent is strong or lacking.
Focus interviews on the most qualified and affordable candidates.
Adjust hiring strategy: reopen roles, change salary budget, or target specific skills.

### Suggestions for Improvement
Increase candidate data over time to improve insights.
Add more skills or certifications for better matching accuracy.
Track recruiter feedback after interviews to refine scoring.
Use conditional formatting or charts for faster visual checks.

This project shows that even simple Excel tools can help recruiters save time, reduce hiring errors, and make smarter decisions.

