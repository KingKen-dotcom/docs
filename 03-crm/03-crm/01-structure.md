# CRM STRUCTURE & DESIGN

## Complete Sheet Design

### Sheet 1: Dashboard

**Purpose:** Executive summary

**Metrics:**
- Total Candidates
- Total Employers
- Active Deals
- Total Revenue (Month)
- Amount Paid
- Outstanding

**Charts:**
- Revenue trend (line)
- Pipeline status (pie)
- Top employers (bar)

**Formulas:**

---

### Sheet 2: Candidates

**Columns:**
| Column | Type | Notes |
|--------|------|-------|
| Candidate ID | Text | C001, C002, etc |
| Full Name | Text | First + Last |
| Phone | Text | +256... format |
| Country | Text | Uganda, Kenya, etc |
| Position | Select | Cleaner, Helper, etc |
| Experience | Number | Years |
| Status | Select | New/Screening/Approved/Deployed/Rejected |
| AI Score | Number | 1-10 |
| Email | Email | Contact |
| CV Link | URL | Google Drive link |
| Passport | Select | Yes/No/Processing |
| Date Applied | Date | Auto-fill |
| Date Approved | Date | When approved |
| Assigned To | Text | Recruiter name |
| Notes | Text | Any info |

---

### Sheet 3: Employers

**Columns:**
| Column | Type |
|--------|------|
| Employer ID | Text |
| Company Name | Text |
| Country | Text |
| Phone | Text |
| Email | Email |
| Contact Person | Text |
| Contact Title | Text |
| Industry | Text |
| Status | Select: Lead/Active/Inactive/Closed |
| Total Spent | Currency |
| Workers Deployed | Number |
| First Contact | Date |
| Last Contact | Date |
| Assigned To | Text |
| Notes | Text |

---

### Sheet 4: Job Requests

**Columns:**
| Column | Type |
|--------|------|
| Job ID | Text |
| Employer Name | Text |
| Position | Text |
| Number Needed | Number |
| Salary | Currency |
| Location | Text |
| Urgency | Select: Low/Medium/High/Critical |
| Description | Text |
| Status | Select: Open/Matching/Filled/Closed |
| Date Created | Date |
| Date Needed | Date |
| Assigned To | Text |
| Candidates Sent | Number |
| Approved | Number |
| Deployed | Number |

---

### Sheet 5: Pipeline Tracker

**Columns:**
| Column | Type |
|--------|------|
| Pipeline ID | Text |
| Candidate Name | Text |
| Employer Name | Text |
| Position | Text |
| Stage | Select: Applied/Screening/Selected/Interview/Processing/Deployed |
| Probability | Percent |
| Expected Close | Date |
| Days in Stage | Number |
| Last Update | Date |
| Notes | Text |
| Assigned To | Text |

---

### Sheet 6: Deals & Revenue

**Columns:**
| Column | Type |
|--------|------|
| Deal ID | Text |
| Employer | Text |
| Workers Sent | Number |
| Fee Per Worker | Currency |
| Total Deal Value | Formula: Workers × Fee |
| Invoice Date | Date |
| Invoice Number | Text |
| Amount Paid | Currency |
| Balance Due | Formula: Total - Paid |
| Status | Select: Pending/Partial/Paid |
| Due Date | Date |
| Date Paid | Date |
| Payment Method | Text |
| Notes | Text |

---

### Sheet 7: Tasks

**Columns:**
| Column | Type |
|--------|------|
| Task ID | Text |
| Description | Text |
| Assigned To | Text |
| Related To | Text |
| Priority | Select: Low/Medium/High |
| Due Date | Date |
| Status | Select: Open/In Progress/Completed/Overdue |
| Date Created | Date |
| Date Completed | Date |
| Notes | Text |

---

### Sheet 8: Contacts

**Columns:**
| Column | Type |
|--------|------|
| Name | Text |
| Company | Text |
| Role | Text |
| Phone | Text |
| Email | Email |
| WhatsApp | Text |
| Type | Select: Employer/Candidate/Partner/Supplier |
| Country | Text |
| Last Contact | Date |
| Notes | Text |

---

## Data Entry Rules

✅ **Candidates:** Auto-filled from form (Zapier) + manual verification  
✅ **Employers:** Add during sales calls  
✅ **Jobs:** Create when employer requests  
✅ **Pipeline:** Update when stage changes  
✅ **Deals:** Create when deal confirmed  
✅ **Tasks:** Create for action items  

❌ Don't delete old records  
❌ Don't change column order  
❌ Don't manually edit auto-filled cells  

---

## Backup Strategy

Every Friday:
1. Right-click sheet
2. Copy to new file
3. Name: "CRM Backup - [Date]"
4. Store in Google Drive "Backups" folder
