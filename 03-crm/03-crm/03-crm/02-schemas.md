# DATABASE SCHEMAS

## Complete Field Definitions

### Candidates Schema

```sql
Candidate ID (Text): C001, C002, C003...
Full Name (Text): First and last name
Phone (Text): International format +256...
Country (Text): Country of residence
Position (Select): Cleaner / Helper / Driver / Cook / Healthcare / Construction / Logistics
Experience (Number): Years in field (0-50)
Status (Select): New / Screening / Approved / Rejected / Deployed
AI Score (Number): 1-10 rating from AI
Email (Email): Personal email
CV Link (URL): Google Drive link to CV
Passport (Select): Yes / No / Processing / Expired
Date Applied (Date): Auto-fill from form
Date Approved (Date): When approved
Assigned To (Text): Recruiter name
Notes (Text): Special requirements or notes
Employer ID (Text): E001, E002, E003...
Company Name (Text): Official company name
Country (Text): Kuwait / UAE / Qatar
Phone (Text): Company phone number
Email (Email): Company email
Contact Person (Text): Main contact name
Contact Title (Text): HR Manager / Owner / Operations
Industry (Text): Cleaning / Logistics / Healthcare / Construction
Status (Select): Lead / Active / Inactive / Closed
Total Spent (Currency): Cumulative spending
Workers Deployed (Number): Total workers sent
First Contact (Date): Initial contact date
Last Contact (Date): Most recent contact
Assigned To (Text): Account manager
Notes (Text): Relationship details
Job ID (Text): J001, J002...
Employer Name (Text): Reference to employer
Position (Text): Job title
Number Needed (Number): Workers required
Salary (Currency): Per worker per month
Location (Text): City/Country
Urgency (Select): Low / Medium / High / Critical
Description (Text): Job requirements
Status (Select): Open / Matching / Filled / Closed
Date Created (Date): When requested
Date Needed (Date): When workers needed
Assigned To (Text): Recruiter handling
Candidates Sent (Number): Count sent
Approved (Number): Count approved
Deployed (Number): Count deployed
Deal ID (Text): D001, D002...
Employer (Text): Company name
Workers Sent (Number): Count deployed
Fee Per Worker (Currency): Commission
Total Deal Value (Formula): Workers × Fee
Invoice Date (Date): When invoiced
Invoice Number (Text): For reference
Amount Paid (Currency): Payment received
Balance Due (Formula): Total - Paid
Status (Select): Pending / Partial / Paid
Due Date (Date): Payment due
Date Paid (Date): When paid
Payment Method (Text): Bank / Cash / Cheque
Notes (Text): Any issues
New → Screening → Approved → Deployed
     or ↓
     Rejected
Lead → Active → Inactive
    or ↓
       Closed
Pending → Partial → Paid
Total Revenue: =SUMIF('Deals & Revenue'!E:E,">0")
Conversion Rate: =COUNTIF(Candidates!H:H,"Approved")/COUNTA(Candidates!A:A)
Average Deal Size: =AVERAGE('Deals & Revenue'!F:F)
Outstanding Payments: =SUMIF('Deals & Revenue'!I:I,">"&0)
Deal Value at Stage: =SUMIF(Pipeline!E:E,"Deployed",'Deals & Revenue'!F:F)
Days in Pipeline: =TODAY()-MIN(Pipeline!I:I)
Win Rate: =COUNTIF(Pipeline!E:E,"Deployed")/COUNTA(Pipeline!A:A)

---

## 📄 **FILE 4: 04-ai-system/README.md**

```markdown
# SECTION 04: AI SYSTEM

## AI-Powered Candidate Screening

Automatically analyze candidates and match them to jobs using ChatGPT.

**Timeline:** Days 10-12  
**Cost:** ~$0.02 per candidate analysis  
**Outcome:** Automated candidate scoring and matching

---

## What Your AI Will Do

✅ Read and analyze CVs  
✅ Score candidates 1-10  
✅ Make hire/reject recommendations  
✅ Match workers to employers  
✅ Detect red flags  
✅ Write candidate summaries  

---

## How It Works

---

## Setup Steps

### Step 1: Create OpenAI Account

1. Visit: platform.openai.com
2. Sign up (use business email)
3. Go to "API keys" section
4. Click "Create new secret key"
5. **Copy key** (save securely!)
6. Add payment method ($5-50/month)

### Step 2: Create Screening Prompt

This is the instruction for ChatGPT:

### Step 3: Connect to Zapier

1. Create new Zap
2. Trigger: Google Forms → New Response
3. Action: OpenAI (ChatGPT)
4. Paste prompt above
5. Map fields: {{name}}, {{position}}, etc.

### Step 4: Update CRM with Results

Add another action:
1. Google Sheets → Update Row
2. Update "Candidates" sheet
3. Set fields:
   - AI Score = ChatGPT score
   - Recommendation = ChatGPT recommendation
   - Notes = ChatGPT explanation

### Step 5: Create Routing Rules (Advanced)

---

## Cost Breakdown

**Per Candidate:**
- Input tokens: ~300 tokens = $0.00015
- Output tokens: ~150 tokens = $0.00045
- Total: ~$0.0006 per candidate

**Monthly Estimates:**
- 100 candidates = $0.06
- 500 candidates = $0.30
- 1,000 candidates = $0.60
- 5,000 candidates = $3.00

**Total Stack Cost:**
- OpenAI: $1-5/month
- Zapier: $20-50/month
- Google Sheets: Free
- **Total: $25-55/month**

---

## Prompt Templates

### Template 1: Standard Screening

### Template 2: Culture Fit

### Template 3: Employer Match

---

## Integration with Workflows

### Workflow 1: Automatic Screening

### Workflow 2: Employer Matching

---

## Important Notes

⚠️ **API Security:**
- Never share your API key
- Store in secure location
- Rotate keys monthly
- Monitor usage

⚠️ **AI Accuracy:**
- AI is helpful, not perfect
- Always review recommendations
- Don't auto-reject without review
- Update prompts based on feedback

⚠️ **Avoid Bias:**
- Monitor if certain groups over/under-scored
- Review decisions for fairness
- Adjust prompts to be objective
- Maintain human oversight

---

## Monitoring & Optimization

**Weekly Review:**
- Check accuracy of scores
- Compare AI recommendations vs actual outcomes
- Gather HR team feedback
- Update prompts if needed

**Metrics to Track:**
- Accuracy rate (% correct)
- Approval rate
- False positive rate (% incorrectly approved)
- False negative rate (% incorrectly rejected)

---

## Checklist

- [ ] OpenAI account created
- [ ] API key secured
- [ ] Zapier + OpenAI connected
- [ ] Screening prompt created & tested
- [ ] AI working on test candidates
- [ ] Scores auto-saved to CRM
- [ ] HR trained on AI output
- [ ] Matching workflow tested
- [ ] Results reviewed for bias
- [ ] Monitoring process in place

---

## Next Steps

✅ AI system integrated  
⏭️ Monitor accuracy and optimize  
⏭️ Expand to employer matching  
⏭️ Build reporting dashboard




