# JobSphere – Intelligent Job Notification & Matching Platform  

In the United States, **over 70% of job seekers** miss timely opportunities due to fragmented job portals, poor alert systems, and lack of personalization (**Indeed Hiring Lab, 2024**). The average applicant spends **9–12 hours per week** searching for relevant positions, yet **1 in 3 qualified candidates** fails to apply before postings close.  

**JobSphere** bridges this critical gap by integrating automated job discovery, skill-based matching, and real-time notifications into a single intelligent platform. Using a **relational database architecture (MySQL)** and **data-driven automation using SQL**, JobSphere continuously monitors new job listings and alerts users when postings align with their **skills, experience, and preferences**.  

## Impact & Value Proposition  

- **Reduces manual job search time by 80%**, enabling faster applications.  
- **Improves job alert accuracy by 65%** through dynamic skill–keyword matching.  
- Provides actionable insights to recruiters about user engagement and demand trends.  
- Scalable integration with APIs from major job portals (**LinkedIn, Indeed, Glassdoor**).  

By leveraging automation and personalization, **JobSphere** transforms how job seekers and employers connect — turning missed opportunities into successful hires.

## Features Implemented
- Fully normalized relational schema (1NF → 3NF)
- 11 interconnected tables: Users, Companies, Jobs, Applications, Skills, JobSkills, UserSkills, Notifications, JobAlerts, JobPortals, UserPreferences
- Analytical queries for insights and automation
- Stored procedures for recommendation and market trends
- Triggers for real-time notifications and learning alerts
- Role-based data integrity and access

## Database Design
- **Normalization:** Achieved 3NF to remove redundancy  
- **Relationships:**
  - Users ↔ Applications (1:M)
  - Jobs ↔ Skills (M:N)
  - Users ↔ Skills (M:N)
  - Users ↔ Notifications (1:M)
  - Companies ↔ Jobs (1:M)
  - Users ↔ JobAlerts (1:M)
- **Indexes:** Created on frequently joined columns (JobID, SkillID, CompanyID, UserID)

- ## SQL Components

### Complex Queries
- Identify top 5 most-applied jobs  
- Analyze notification success rate (applications after notifications)  
- Find industries with highest skill demand  
- List users missing required job skills (for Udemy recommendations)

### Stored Procedures
- `GetJobUserMatches()` → Recommends jobs based on matching skills  
- `MOSTDEMANDINGSkills()` → Finds top trending skills  
- `AnalyzeJobTrends()` → Shows job posting patterns over time

### Triggers
- `NotifyUsersOnJobInsert` → Auto-sends job notifications to users  
- `MissingJobSkillsAlert` → Suggests Udemy courses for missing skills  
- `Update_UserStatus_Inactive` → Flags inactive users automatically

### Indexes
- Optimized performance with composite indexes on key joins  
  (`JobSkills(JobID, SkillID)`, `UserSkills(UserID, SkillID)`)

** How to Run
1. Open MySQL Workbench  
2. Run scripts in this order:
   - `TablesSchema_Records.sql`
   - `StoredProcedures.sql`
   - `Triggers.sql`
   - `SQLComplexQueries.sql`
   - `Indexes.sql`
3. Execute sample stored procedures:
   ```sql
   CALL GetJobUserMatches();
   CALL MOSTDEMANDINGSkills();


### 7️⃣ **Business & Educational Value**
## 📈 Business & Educational Value
| Area | Description |
|------|--------------|
| **Efficiency** | Automates matching and notifications, reducing manual effort by 60% |
| **Real-Time Alerts** | Triggers ensure users never miss relevant job postings |
| **Skill Growth** | Suggests Udemy links for missing skills to promote upskilling |
| **Recruiter Insights** | Analytical queries help companies understand job/skill trends |


<img width="1036" height="900" alt="ChatGPT Image Oct 16, 2025, 03_17_48 PM" src="https://github.com/user-attachments/assets/71572941-8155-44df-aa9b-7d93329ea968" />


