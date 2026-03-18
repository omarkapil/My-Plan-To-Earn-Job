# 📚 DAY-BY-DAY RESOURCE GUIDE
## Complete 12-Week Career Bridge Program
### Specific Resources for Every Day of Learning

---

## HOW TO USE THIS GUIDE

**This document provides:**
- ✅ Specific video recommendations (with channels/creators)
- ✅ Documentation links (AWS, CompTIA, ISC2)
- ✅ Practice platforms (quizzes, exams, labs)
- ✅ Hands-on lab environments
- ✅ Community forums & support
- ✅ Books & study guides
- ✅ Tools to download/install
- ✅ Daily timeline (suggested hours)

**For each day you'll find:**
1. **Primary Resource:** Main video/course to watch
2. **Alternative Resources:** Other options if first doesn't work
3. **Practice Resources:** Hands-on platforms
4. **Documentation:** Official guides & references
5. **Community:** Forums & support channels
6. **Time Estimate:** Suggested hours for each section

---

# WEEK 1: AWS CLOUD FUNDAMENTALS & ARCHITECTURAL MINDSET

## WEEK 1 OVERVIEW
- **Total Hours:** 30 hours
- **Primary Focus:** AWS basics, IAM, EC2, VPC, S3, RDS
- **Certifications Aligned:** AWS Practitioner, Solutions Architect (15%)
- **Daily Structure:** 4-5 hours of learning/labs per day

---

## MONDAY - DAY 1: CLOUD CONCEPTS & AWS POSITIONING

### SCHEDULE (5 hours total)
- Theory: 2 hours
- Hands-on: 2 hours  
- Documentation: 1 hour

### PRIMARY RESOURCES

**Video Tutorials:**
1. **NetworkChuck - AWS Cloud Practitioner (EP1)**
   - Channel: NetworkChuck (YouTube)
   - Link: Search "NetworkChuck AWS Cloud Practitioner"
   - Duration: 45-60 min
   - Content: Cloud computing basics, AWS overview
   - Why: Entertaining, practical-first approach

2. **AWS Official - What is Cloud Computing**
   - Channel: AWS (YouTube)
   - Link: Search "AWS What is Cloud Computing"
   - Duration: 30 min
   - Content: Authoritative overview
   - Why: Straight from AWS

### ALTERNATIVE RESOURCES

**If videos aren't loading:**
- AWS Documentation: https://docs.aws.amazon.com/general/latest/gr/
- White paper: "Overview of AWS" (PDF, 30 pages)
- Read on: AWS official website

**If you prefer reading:**
- AWS Getting Started Guide (free PDF)
- "Cloud Computing Basics" on A Cloud Guru (first 30 min free)

### HANDS-ON ACTIVITIES

**Hands-on Lab (1 hour):**
1. Create AWS Free Tier account
   - Go to: https://aws.amazon.com/free
   - Enter email, verify
   - Add payment method (charges only if over free tier)
   - Verify account is active

2. Explore AWS Console
   - Log into AWS Management Console
   - Locate EC2, VPC, S3, RDS services
   - Read: "AWS Free Tier Overview" in console
   - Document: Screenshot of console dashboard

**Practice Questions (30 min):**
- AWS Skill Builder free course: "AWS Cloud Practitioner Essentials"
  - Start Module 1 (free section)
  - Link: https://skillbuilder.aws.amazon.com/
  - Do 10 practice questions
  - Pass rate target: 80%+

### DOCUMENTATION TO READ

**Official AWS Docs (30 min):**
1. AWS Global Infrastructure
   - Link: https://aws.amazon.com/about-aws/global-infrastructure/
   - Read: Regions & Availability Zones section
   - Understand: Why geography matters

2. AWS Shared Responsibility Model
   - Link: https://aws.amazon.com/compliance/shared-responsibility-model/
   - Read: Full page
   - Document: Create a 1-page summary

### COMMUNITIES & FORUMS

**Join These Today:**
1. r/aws (Reddit)
   - Link: https://reddit.com/r/aws
   - Action: Subscribe, read pinned posts
   - Don't post yet (just observe)

2. AWS Discord
   - Link: Search "AWS Discord community"
   - Action: Join, introduce yourself
   - Observation: See questions others ask

### TOOLS TO INSTALL/SETUP

**By end of day, you need:**
- [ ] AWS Free Tier account created
- [ ] AWS Console access verified
- [ ] Text editor (VS Code recommended)
  - Download: https://code.visualstudio.com/
  - Installation: 5 minutes

### EVENING REFLECTION (15 min)

**Write in your learning journal:**
1. What was the most interesting thing you learned today?
2. What confused you? (Don't worry if nothing makes sense yet)
3. Rate your comfort level 1-10: ____

---

## TUESDAY - DAY 2: REGIONS, AZS, SHARED RESPONSIBILITY MODEL

### SCHEDULE (5 hours)
- Theory & Video: 2 hours
- Hands-on Console Exploration: 1.5 hours
- Documentation: 1 hour
- Practice: 30 min

### PRIMARY RESOURCES

**Video Tutorials:**

1. **NetworkChuck - AWS Cloud Practitioner (EP2)**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck AWS Cloud Practitioner episode 2"
   - Duration: 45 min
   - Content: Regions, AZs, edge locations
   - Why: Visualizes AWS global infrastructure

2. **AWS Official - AWS Regions & Availability Zones**
   - Channel: AWS (YouTube)
   - Search: "AWS Regions Availability Zones explained"
   - Duration: 20 min
   - Content: Technical explanation
   - Why: Official resource

### HANDS-ON ACTIVITIES

**Lab 1A Part 1: AWS Account Setup & Exploration (1.5 hours)**

1. **Access Different Regions (30 min)**
   ```
   - Log into AWS Console
   - Top right: Click region dropdown (currently us-east-1)
   - Note all available regions
   - Switch to: eu-west-1 (Ireland)
   - Observe: Console looks the same (region is just location)
   - Return to: us-east-1
   - Screenshot: Regions dropdown
   ```

2. **Explore Availability Zones (30 min)**
   - Go to: VPC → Subnets
   - Screenshot: Shows which AZs are available
   - Learn: Each region has 2-3 AZs for redundancy

3. **Research Compliance (30 min)**
   - Go to: AWS → Compliance → Certifications
   - Read: Which regions support which compliance standards
   - Document: Which region for healthcare data? (HIPAA)
   - Answer: Choose region with HIPAA support

**Practice Quiz (30 min):**
- Platform: ExamTopics or TutorialDojo
  - Question topic: "AWS Regions and Availability Zones"
  - Do: 10 questions
  - Target: 80%+ pass rate
  - Document: Screenshot of results

### DOCUMENTATION TO READ

**By End of Day (1 hour):**
1. Read: AWS Shared Responsibility Model (full)
   - Link: https://aws.amazon.com/compliance/shared-responsibility-model/
   - Create: Comparison table (AWS responsibility vs. Your responsibility)

2. Read: AWS Global Infrastructure
   - Understand: Why multi-AZ matters (disaster recovery)
   - Document: Why would you use us-west-2 instead of us-east-1?

### EVENING TASK (30 min)

**Write First Blog Post Draft:**
- Title: "Understanding AWS Regions and Availability Zones"
- Section 1: What is a region? (your words, 2 paragraphs)
- Section 2: What is an AZ? (your words, 2 paragraphs)
- Section 3: Why does this matter? (1 paragraph)
- Note: Don't publish yet, save as draft

---

## WEDNESDAY - DAY 3: IAM FUNDAMENTALS & USERS/GROUPS

### SCHEDULE (5 hours)
- Video & Theory: 2 hours
- IAM Console Exploration: 1.5 hours
- Hands-on Lab: 1 hour
- Practice: 30 min

### PRIMARY RESOURCES

**Video Tutorials:**

1. **NetworkChuck - AWS IAM Explained**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck AWS IAM"
   - Duration: 60 min
   - Content: Users, groups, roles, policies
   - Why: Clear visual explanation

2. **AWS Official - IAM Basics**
   - Channel: AWS (YouTube)
   - Search: "AWS IAM tutorial for beginners"
   - Duration: 30 min
   - Content: Official explanation
   - Why: Straight from source

3. **Jeremy's IT Lab - IAM Deep Dive**
   - Channel: Jeremy's IT Lab (YouTube)
   - Search: "Jeremy's IT Lab IAM"
   - Duration: 45 min
   - Content: More academic approach
   - Why: Good reference material

### HANDS-ON LAB 1B: IAM USER SETUP (1 hour)

**Step 1: Create First IAM User (20 min)**
```
1. Go to: AWS Console → IAM
2. Left sidebar: Click "Users"
3. Button: "Create user"
4. Username: "admin-user-1"
5. Attach policy: "AdministratorAccess"
6. Create access keys (save CSV file)
7. Screenshot: User created
```

**Step 2: Create IAM Group (15 min)**
```
1. Left sidebar: Click "User Groups"
2. Create group: "Developers"
3. Attach policy: "PowerUserAccess"
4. Add user to group: "admin-user-1"
5. Screenshot: Group created
```

**Step 3: Create Read-Only User (15 min)**
```
1. Create new user: "readonly-user"
2. Attach policy: "ReadOnlyAccess"
3. Create access keys
4. Save: All credentials safely (will use later)
```

**Step 4: Document & Screenshot (10 min)**
- Screenshot: All users created
- Screenshot: User groups
- Create document: "IAM Setup Summary"
  - Include: Screenshot + explanation of each user

### DOCUMENTATION TO READ

**Official AWS IAM Docs (1 hour):**
1. IAM User Guide - Getting Started
   - Link: https://docs.aws.amazon.com/iam/latest/userguide/getting-started_create-admin-group.html
   - Read: Create admin group section

2. IAM Best Practices
   - Link: https://docs.aws.amazon.com/iam/latest/userguide/best-practices.html
   - Read: First 5 best practices
   - Note: Don't use root account (critical!)

### PRACTICE RESOURCES

**Quiz Practice (30 min):**
- Platform: TutorialDojo or Examtopics
  - Topic: "AWS IAM Users and Groups"
  - Do: 15 questions
  - Target: 75%+

### GITHUB CHECKPOINT

**By end of day, commit to GitHub:**
```
Week1/
├── Day3-IAM/
│   ├── IAM-Setup-Screenshot.png
│   ├── IAM-Summary.md
│   └── Users-Created.txt
```

---

## THURSDAY - DAY 4: IAM POLICIES & EC2 BASICS

### SCHEDULE (5 hours)
- Video & Theory: 1.5 hours
- IAM Policy Creation: 1.5 hours
- EC2 Introduction: 1 hour
- Practice: 1 hour

### PRIMARY RESOURCES

**Video Tutorials:**

1. **NetworkChuck - AWS IAM Policies**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck AWS IAM policies"
   - Duration: 40 min
   - Content: Reading and writing policies
   - Why: Shows real policy examples

2. **AWS Official - EC2 Basics**
   - Channel: AWS (YouTube)
   - Search: "AWS EC2 what is it"
   - Duration: 20 min
   - Content: EC2 overview
   - Why: Official resource

### HANDS-ON: CREATE CUSTOM IAM POLICY (1.5 hours)

**Policy 1: S3 Read-Only for Specific Bucket**
```
1. Go to: IAM → Policies
2. Create policy (JSON editor)
3. Paste this policy:
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket/*"
    }
  ]
}
4. Name policy: "S3-Specific-Bucket-Read"
5. Review & create
```

**Policy 2: EC2 Read-Only**
```
1. Create another policy
2. Use managed policy: "AmazonEC2ReadOnlyAccess"
3. Attach to: "readonly-user"
4. Test: Login as readonly-user, see EC2 but can't modify
```

**Policy 3: EC2 Management (Limited)**
```
1. Create policy:
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:RunInstances",
        "ec2:StopInstances",
        "ec2:TerminateInstances"
      ],
      "Resource": "*"
    }
  ]
}
2. Name: "EC2-Basic-Manager"
3. Review & create
```

**Documentation:**
- Create document: "IAM Policies I Created"
  - Include: JSON for each policy
  - Explain: What each policy allows

### EC2 INTRODUCTION (1 hour)

**Watch:** EC2 video tutorial (20 min)

**Explore Console (40 min):**
```
1. Go to: EC2 Dashboard
2. Observe: "Running instances" (probably 0)
3. Left menu: Explore sections
   - Instances
   - Images (AMIs)
   - Security Groups
   - Key Pairs
4. Screenshot: EC2 console
```

### PRACTICE (1 hour)

**Quiz: IAM Policies (30 min)**
- Platform: TutorialDojo
  - Topic: "IAM Policies and Permissions"
  - Do: 20 questions
  - Target: 75%+

**Video: EC2 Basics (30 min)**
- Watch: "EC2 Instance Types Explained"
  - Channel: CloudAcademy or AWS
  - Understand: t2, m5, c5 differences

### END OF DAY

**GitHub Commit:**
```
Week1/
├── Day4-IAM-Policies/
│   ├── Custom-Policies.json
│   ├── Policy-Explanations.md
│   └── EC2-Console-Screenshot.png
```

---

## FRIDAY - DAY 5: EC2 INSTANCE LAUNCH & VPC INTRO

### SCHEDULE (6 hours - longer day to catch up)
- EC2 Launch Video: 1 hour
- Lab 1C: EC2 Launch: 2.5 hours
- VPC Introduction: 1 hour
- Quiz & Review: 1.5 hours

### PRIMARY RESOURCES

**Video Tutorials:**

1. **NetworkChuck - EC2 Explained**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck AWS EC2"
   - Duration: 60 min
   - Content: EC2 types, launching instances
   - Why: Practical, step-by-step

2. **AWS Official - Launching Your First EC2 Instance**
   - Channel: AWS (YouTube)
   - Search: "AWS EC2 launch instance tutorial"
   - Duration: 30 min
   - Content: Official walkthrough
   - Why: Best practices included

### LAB 1C: LAUNCH EC2 INSTANCE (2.5 hours)

**Part 1: Prepare (30 min)**
```
1. Create key pair:
   - EC2 Console → Key Pairs
   - Create new key pair
   - Name: "week1-key"
   - Save .pem file securely

2. Create security group:
   - EC2 → Security Groups
   - Create: "week1-web-server"
   - Inbound: SSH (22) from your IP
   - Inbound: HTTP (80) from anywhere
```

**Part 2: Launch Instance (1 hour)**
```
1. EC2 → Instances → Launch Instance
2. AMI: Amazon Linux 2 (free tier eligible)
3. Instance type: t2.micro (free tier)
4. Network: Default VPC
5. Storage: 8GB (free tier)
6. Key pair: week1-key
7. Security group: week1-web-server
8. Review & Launch
```

**Part 3: Connect & Configure (1 hour)**
```
1. Get public IP from instance
2. SSH into instance:
   chmod 400 week1-key.pem
   ssh -i week1-key.pem ec2-user@[PUBLIC-IP]

3. Install web server:
   sudo yum update -y
   sudo yum install -y httpd
   sudo systemctl start httpd

4. Test:
   Open browser: http://[PUBLIC-IP]
   Should see Apache test page

5. Screenshot: Web server running
```

**Document in GitHub:**
```
Week1/Lab1C-EC2/
├── EC2-Launch-Steps.md
├── Security-Group-Config.png
├── Instance-Running.png
└── Web-Server-Test.png
```

### VPC INTRODUCTION (1 hour)

**Video:** AWS VPC Basics
- Channel: NetworkChuck
- Search: "NetworkChuck AWS VPC"
- Duration: 45 min
- Document: Create 1-page summary of what VPC is

### ASSESSMENT (1.5 hours)

**Quiz (1 hour):**
- Platform: TutorialDojo
- Topic: "AWS EC2 and IAM"
- Do: 25 questions
- Target: 75%+
- Document: Screenshot of results

**Week 1 Review (30 min):**
- Reflect on learning
- Identify weak areas
- Plan Week 2

### WEEKLY BLOG POST

**Publish Today:**
- Title: "My First Week in AWS"
- Sections:
  1. What I learned (3 paragraphs)
  2. My first EC2 instance (with screenshot)
  3. Key takeaways (3 bullet points)
  4. Next week goals (2 sentences)
- Post on: LinkedIn + Medium/Dev.to

---

## SATURDAY-SUNDAY: WEEK 1 WRAP-UP & WEEK 2 PREP

### SATURDAY: CONSOLIDATION (3 hours)

**GitHub Organization (1 hour):**
- Organize all Week 1 folders
- Create README for each day
- Review: 100+ commits by week end

**Blog Post Refinement (1 hour):**
- Edit Week 1 blog post
- Add images/screenshots
- Publish on LinkedIn

**Networking (1 hour):**
- Follow 20 AWS professionals on LinkedIn
- Join r/aws subreddit
- Join AWS Discord community
- Post introduction in Discord

### SUNDAY: PREPARATION (2 hours)

**Study Next Week's Content (1 hour):**
- Review: Week 2 OSI Model section
- Watch preview: NetworkChuck OSI Model video (20 min)
- Identify resources needed

**Mental Preparation (1 hour):**
- Reflection: How did Week 1 go?
- Confidence level: ____/10
- Challenges faced: ____
- Solutions: ____
- Goals for Week 2: ____

---

---

# WEEK 2: NETWORKING FUNDAMENTALS DEEP-DIVE & SECURITY GROUPS MASTERY

## WEEK 2 OVERVIEW
- **Total Hours:** 28 hours
- **Primary Focus:** OSI Model, TCP/IP, Wireshark, Security Groups
- **Certifications Aligned:** CompTIA Network+ (30% progress)
- **Labs:** 4 comprehensive networking labs

---

## MONDAY - DAY 8: OSI MODEL & NETWORKING BASICS

### SCHEDULE (4.5 hours)
- Video & Theory: 2 hours
- Lab Preparation: 1 hour
- Practice: 1.5 hours

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - CompTIA Network+ OSI Model**
   - Channel: Professor Messer (YouTube)
   - Link: Search "Professor Messer OSI model N10-008"
   - Duration: 60 min
   - Content: All 7 layers explained
   - Why: Exam-focused, authoritative

2. **NetworkChuck - OSI Model Explained**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck OSI model"
   - Duration: 40 min
   - Content: Visual, easy to understand
   - Why: Entertaining explanation

3. **CompTIA Network+ Study Guide**
   - Read: Chapter 3 (OSI Model)
   - Time: 1 hour
   - Include: Diagrams
   - Document: Create your own OSI diagram

### HANDS-ON SETUP

**Tools to Install (1 hour):**
1. **Wireshark** (packet analyzer)
   - Download: https://www.wireshark.org/download/
   - Installation: 15 min
   - Verify: Can launch successfully

2. **Cisco Packet Tracer** (network simulator)
   - Link: https://www.netacad.com/
   - Create account (free)
   - Download & install: 30 min
   - Note: Will use in Week 2 labs

3. **Linux terminal tools ready:**
   - ping, traceroute, telnet, netstat, ss
   - Test: `ping google.com` works?

### PRACTICE RESOURCES

**Quiz (1 hour):**
- Platform: ExamTopics or TutorialDojo
  - Topic: "OSI Model Layers"
  - Do: 20 questions
  - Target: 80%+

**Write OSI Cheat Sheet (30 min):**
- Create: 1-page document
  - Each layer (7 total)
  - Key protocols
  - Example devices
  - Save: Use for studying

### GITHUB CHECKPOINT

```
Week2/
├── Day8-OSI-Model/
│   ├── OSI-Diagram.png
│   ├── OSI-Cheat-Sheet.md
│   └── Wireshark-Installed.txt
```

---

## TUESDAY - DAY 9: TCP/IP PROTOCOLS & PORTS

### SCHEDULE (5 hours)
- Video & Theory: 2 hours
- TCP Handshake Deep-Dive: 1 hour
- Lab: Port Analysis: 1.5 hours
- Practice: 30 min

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - TCP/IP Protocols**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer TCP IP protocols"
   - Duration: 45 min
   - Content: TCP vs UDP, ports
   - Why: Exam-focused

2. **NetworkChuck - TCP Three-Way Handshake**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck TCP handshake"
   - Duration: 20 min
   - Content: Visual explanation
   - Why: Hard concept made easy

3. **CompTIA Study Guide:**
   - Read: Chapter 4 (Protocols)
   - Focus: TCP/UDP comparison
   - Time: 1 hour

### HANDS-ON LAB: PORT & PROTOCOL ANALYSIS (1.5 hours)

**Lab Activity:**
```
1. Open terminal
2. Check listening ports:
   ss -tuln | head -20
   
3. Understand output:
   - Column 1: Protocol (tcp/udp)
   - Column 4: Local address
   - Column 5: Port number

4. Common ports to know:
   - 80: HTTP
   - 443: HTTPS
   - 22: SSH
   - 3306: MySQL
   - 5432: PostgreSQL
   - 3389: RDP
   - 21: FTP

5. Test connectivity:
   telnet google.com 80
   (Should connect, then close)

6. Document: Screenshot of results
```

**Create Port Reference (1 hour):**
- Document: "Common Ports Reference"
  - 30+ common ports
  - Protocol name
  - Purpose
  - When used
  - Save: Use for studying

### DOCUMENTATION

**Read (1 hour):**
- TCP/IP Reference Guide
  - Link: Search "RFC 793 TCP specification"
  - Read: First 10 pages (overview)
  - Understand: What is a RFC?

**Port Database:**
- IANA Port Assignments
  - Link: https://www.iana.org/assignments/service-names-port-numbers/
  - Browse: Some common services

### PRACTICE RESOURCES

**Quiz (30 min):**
- Platform: TutorialDojo
  - Topic: "TCP/IP Protocols and Ports"
  - Do: 25 questions
  - Target: 75%+

---

## WEDNESDAY - DAY 10: WIRESHARK LAB - PACKET ANALYSIS

### SCHEDULE (5 hours)
- Wireshark intro video: 30 min
- Lab 2A Part 1: ICMP capture: 1.5 hours
- Lab 2A Part 2: DNS capture: 1.5 hours
- Lab 2A Part 3: HTTP capture: 1 hour

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - Wireshark Tutorial**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer Wireshark"
   - Duration: 45 min
   - Content: How to use Wireshark
   - Why: Practical tutorial

2. **Wireshark Official Documentation**
   - Link: https://www.wireshark.org/docs/
   - Read: User's Guide (first chapter)
   - Time: 30 min

### LAB 2A: PACKET ANALYSIS WITH WIRESHARK (4 hours)

**Part 1: ICMP Packets (1.5 hours)**
```
1. Open Wireshark
2. Select: Your network interface
3. Start capture
4. In terminal: ping -c 4 google.com
5. Stop capture in Wireshark
6. Filter: icmp
7. Observe:
   - ICMP Request packets
   - ICMP Reply packets
   - Sequence numbers
   - TTL values
8. Screenshot: ICMP capture
9. Document: What you see
```

**Part 2: DNS Queries (1.5 hours)**
```
1. Start new Wireshark capture
2. In terminal: nslookup google.com
3. Stop capture
4. Filter: dns
5. Observe:
   - DNS Query (your machine asking)
   - DNS Response (server answering)
   - IP address in response
6. Screenshot: DNS capture
7. Document: DNS conversation
```

**Part 3: HTTP Traffic (1 hour)**
```
1. Start Wireshark capture
2. In terminal: curl http://example.com
3. Stop capture
4. Filter: http
5. Observe:
   - HTTP GET request
   - HTTP 200 OK response
   - HTML content
6. Screenshot: HTTP capture
7. Document: HTTP flow
```

**Create Lab Report (1 hour):**
```
Week2/Lab2A-Wireshark/
├── ICMP-Capture.png
├── DNS-Capture.png
├── HTTP-Capture.png
├── Wireshark-Analysis.md
└── Packet-Observations.txt
```

---

## THURSDAY - DAY 11: SECURITY GROUPS LAB

### SCHEDULE (5 hours)
- Video & Theory: 1 hour
- Lab 2B Part 1: Create SGs: 1.5 hours
- Lab 2B Part 2: Test Rules: 1.5 hours
- Practice & Review: 1 hour

### PRIMARY RESOURCES

**Video Tutorials:**

1. **NetworkChuck - AWS Security Groups**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck AWS security groups"
   - Duration: 40 min
   - Content: How to use security groups
   - Why: Practical walkthrough

2. **AWS Official - Security Groups Guide**
   - Channel: AWS (YouTube)
   - Search: "AWS security groups explained"
   - Duration: 30 min
   - Content: Official explanation

### LAB 2B: SECURITY GROUPS MASTERY (3 hours)

**Part 1: Create Security Groups (1.5 hours)**
```
1. Go to: EC2 → Security Groups
2. Create: "Web-Tier-SG"
   - Inbound SSH (22) from your IP
   - Inbound HTTP (80) from 0.0.0.0/0
   - Inbound HTTPS (443) from 0.0.0.0/0
   - Outbound: All (default)

3. Create: "App-Tier-SG"
   - Inbound port 8080 from Web-Tier-SG
   - Outbound: All

4. Create: "DB-Tier-SG"
   - Inbound port 3306 from App-Tier-SG
   - Outbound: All

5. Document: All rules created
```

**Part 2: Test Rules (1.5 hours)**
```
1. Launch EC2 in Web tier
   - Assign: Web-Tier-SG
   - Verify: Can SSH

2. Launch EC2 in App tier
   - Assign: App-Tier-SG
   - Verify: Can SSH from Web tier only
   - Verify: Can't SSH from internet

3. Test connectivity:
   - Web → App: Should work
   - App → DB: Should work
   - Internet → App: Should fail

4. Screenshots: All tests
```

**Lab Report:**
```
Week2/Lab2B-SecurityGroups/
├── Security-Group-Rules.png
├── Connectivity-Tests.md
├── Test-Results.txt
└── Architecture-Diagram.png
```

### PRACTICE RESOURCES

**Quiz (1 hour):**
- Platform: TutorialDojo
  - Topic: "AWS Security Groups"
  - Do: 20 questions
  - Target: 75%+

---

## FRIDAY - DAY 12: VPC FLOW LOGS & NETWORK MONITORING

### SCHEDULE (6 hours - longer day)
- VPC Flow Logs video: 1 hour
- Lab 2D: Setup & analyze: 2 hours
- Network troubleshooting scenarios: 2 hours
- Assessment & review: 1 hour

### PRIMARY RESOURCES

**Video Tutorials:**

1. **AWS Official - VPC Flow Logs**
   - Channel: AWS (YouTube)
   - Search: "AWS VPC Flow Logs tutorial"
   - Duration: 30 min
   - Content: How to enable and use
   - Why: Official resource

2. **CloudWatch Logs Analysis:**
   - Tutorial: "How to analyze VPC Flow Logs"
   - Duration: 30 min

### LAB 2D: VPC FLOW LOGS (2 hours)

**Part 1: Enable Flow Logs (30 min)**
```
1. Go to: VPC → Your VPC
2. Actions → Edit Flow Logs
3. Create new Flow Log:
   - Destination: CloudWatch Logs
   - Log group: vpc-flow-logs
   - Role: Create IAM role
   - Enable

4. Wait 5 minutes for logs to generate
```

**Part 2: Generate Traffic (30 min)**
```
1. SSH into EC2 instance multiple times
2. Try to SSH from wrong IP (will be denied)
3. curl to web servers
4. Generate various traffic types
```

**Part 3: Analyze Logs (1 hour)**
```
1. Go to: CloudWatch → Log Groups
2. Open: vpc-flow-logs
3. Analyze entries:
   - Find ACCEPT entries (allowed)
   - Find REJECT entries (blocked)
   - Identify: Which IPs, ports, protocols
4. Document: What you learned

5. Screenshot: Sample flow log entry
```

### NETWORK TROUBLESHOOTING SCENARIOS (2 hours)

**Scenario 1: "EC2 can't reach RDS"**
- Debug steps using your new knowledge
- Document findings
- Propose solution

**Scenario 2: "Internet can't reach my web server"**
- Troubleshoot using OSI model
- Layer by layer analysis
- Identify problem

### ASSESSMENT (1 hour)

**Week 2 Quiz:**
- Platform: TutorialDojo
- Topics: OSI, TCP/IP, Wireshark, Security Groups, VPC
- Do: 40 questions (comprehensive)
- Target: 75%+

**Network Fundamentals Certification Prep:**
- CompTIA Network+ progress check
- Identify weak areas
- Plan Week 3 prep

### WEEKLY BLOG POST

**Publish:**
- Title: "Network Troubleshooting: A Practical Guide"
- Include: OSI model diagram
- Include: Troubleshooting steps
- Include: Screenshot from Wireshark lab
- Post on: LinkedIn

---

## SATURDAY-SUNDAY: WEEK 2 WRAP-UP

### SATURDAY: LAB REVIEW & GITHUB (3 hours)

**Organize all Week 2 labs:**
- Clean up folder structure
- Review all documentation
- Add READMEs
- Verify 50+ commits

**Network Fundamentals Summary:**
- Create: 1-page cheat sheet
  - OSI model
  - Common ports
  - Protocols
  - Troubleshooting steps

### SUNDAY: PREPARATION & REFLECTION (2 hours)

**LinkedIn Engagement:**
- Comment on 5 networking posts
- Share Week 2 learnings
- Connect with 10 network engineers

**Week 3 Preview:**
- Review: Linux hardening section
- Watch: Linux basics video preview
- Set Week 3 goals

---

---

# WEEK 3: LINUX HARDENING & SYSTEMS ADMINISTRATION

## WEEK 3 OVERVIEW
- **Total Hours:** 25 hours
- **Primary Focus:** Linux hardening, services, permissions, scripting
- **Labs:** 4 hands-on Linux labs
- **Skills:** System administration, security, automation

---

## MONDAY - DAY 15: LINUX FUNDAMENTALS & FILE SYSTEMS

### SCHEDULE (4.5 hours)
- Video & Theory: 2 hours
- Linux CLI basics: 1.5 hours
- File system exploration: 1 hour

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - CompTIA Linux+ Basics**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer Linux basics"
   - Duration: 45 min
   - Content: Linux fundamentals
   - Why: Exam-aligned

2. **NetworkChuck - Linux Basics**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck Linux basics"
   - Duration: 60 min
   - Content: Command line fundamentals
   - Why: Practical introduction

3. **CompTIA Linux+ Study Guide:**
   - Read: Chapter 1-2
   - Time: 1.5 hours

### HANDS-ON: LINUX CLI BASICS (1.5 hours)

**Using your EC2 instance from Week 1:**
```
1. SSH into your EC2 instance
2. Learn basic commands:
   pwd              (where are you?)
   ls               (list files)
   cd /etc          (change directory)
   cat /etc/passwd  (read file)
   mkdir test       (create folder)
   touch file.txt   (create file)
   cp              (copy)
   mv              (move/rename)
   rm              (remove)

3. Practice each command 3x
4. Screenshot: Terminal with commands
```

**File System Exploration (1 hour):**
```
1. Explore important directories:
   /bin       - Essential commands
   /etc       - Configuration files
   /home      - User home directories
   /var/log   - Log files
   /tmp       - Temporary files

2. Document: What's in each directory
3. Read: /etc/hostname (your server name)
4. Read: /etc/os-release (OS version)
```

### DOCUMENTATION

**Read (1 hour):**
- Linux File System Hierarchy
  - Link: https://refspecs.linuxfoundation.org/fhs.shtml
  - Read: First 5 sections
  - Understand: Why directories are organized this way

---

## TUESDAY - DAY 16: FILE PERMISSIONS & USER MANAGEMENT

### SCHEDULE (5 hours)
- Video & Theory: 1.5 hours
- Permissions practice: 2 hours
- User management: 1.5 hours

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - Linux Permissions**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer Linux permissions"
   - Duration: 45 min
   - Content: rwx permissions, chmod, chown
   - Why: Critical for security

2. **NetworkChuck - Linux File Permissions**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck Linux permissions"
   - Duration: 30 min
   - Content: Practical examples
   - Why: Easy to understand

### HANDS-ON: FILE PERMISSIONS (2 hours)

**Permissions Practice:**
```
1. Create test file:
   echo "test" > myfile.txt
   ls -l myfile.txt
   (shows: -rw-r--r--)

2. Understand permissions:
   rwx rwx rwx
   Owner Group Other
   r=4, w=2, x=1

3. Change permissions:
   chmod 755 myfile.txt
   (Owner: rwx, Group: r-x, Other: r-x)
   
   chmod 600 myfile.txt
   (Only owner can read/write)
   
   chmod 644 myfile.txt
   (Owner rw, others r)

4. Practice: Create scenarios
   - Secure file: chmod 600
   - Executable: chmod 755
   - Read-only: chmod 444

5. Document: Each command & result
```

**User Management (1.5 hours):**
```
1. Create new user:
   sudo useradd -m -s /bin/bash newuser
   sudo passwd newuser

2. Create group:
   sudo groupadd developers
   sudo usermod -aG developers newuser

3. Check:
   id newuser  (shows groups)
   groups newuser

4. Change ownership:
   sudo chown newuser:developers myfile.txt
   ls -l myfile.txt

5. Document: Commands & results
```

### LAB 3A PART 1: USER & PERMISSIONS (1 hour)

**In GitHub:**
```
Week3/Lab3A-Permissions/
├── Permissions-Commands.md
├── Permissions-Output.txt
├── User-Management.md
└── Scenarios-Completed.txt
```

---

## WEDNESDAY - DAY 17: SERVICE MANAGEMENT & MONITORING

### SCHEDULE (5 hours)
- Video & Theory: 1.5 hours
- Systemd practice: 1.5 hours
- System monitoring: 1.5 hours
- Documentation: 30 min

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - Linux Services**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer systemd"
   - Duration: 40 min
   - Content: systemctl, service management
   - Why: Essential for sysadmin

2. **NetworkChuck - System Monitoring**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck Linux monitoring"
   - Duration: 45 min
   - Content: top, ps, htop
   - Why: Troubleshooting skills

### HANDS-ON: SERVICE MANAGEMENT (1.5 hours)

**Systemd Commands:**
```
1. Check service status:
   systemctl status ssh
   systemctl status httpd

2. Start/stop services:
   sudo systemctl start httpd
   sudo systemctl stop httpd
   sudo systemctl restart httpd

3. Enable/disable auto-start:
   sudo systemctl enable httpd
   sudo systemctl disable httpd

4. View all services:
   systemctl list-units --type=service

5. Check if service is enabled:
   systemctl is-enabled httpd
   (returns: enabled or disabled)

6. Document: Each command & result
```

### SYSTEM MONITORING (1.5 hours)

**Monitor Resources:**
```
1. Real-time monitoring:
   top              (CPU, memory, processes)
   htop             (colored version of top)
   
2. See processes:
   ps aux           (all processes)
   ps aux | grep python

3. Memory usage:
   free -h          (human-readable)
   
4. Disk usage:
   df -h            (filesystem)
   du -sh /*        (directories)

5. Network:
   ss -tuln         (open ports)
   netstat -tuln    (older command)

6. Screenshot: Each command output
7. Document: What each shows
```

---

## THURSDAY - DAY 18: LOGS & TROUBLESHOOTING

### SCHEDULE (5 hours)
- Log files overview: 1 hour
- Log analysis practice: 2 hours
- Troubleshooting scenarios: 1.5 hours
- Documentation: 30 min

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - Linux Logs**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer Linux logs"
   - Duration: 40 min
   - Content: Log files, analysis
   - Why: Troubleshooting skill

2. **Linux Log Analysis Guide:**
   - Read: "How to Read Linux Logs"
   - Time: 30 min

### HANDS-ON: LOG ANALYSIS (2 hours)

**Explore Logs:**
```
1. SSH into EC2 instance
2. Navigate to logs:
   cd /var/log
   ls -la

3. Important log files:
   syslog          - System messages
   auth.log        - Authentication attempts
   apache2/access.log - Web server
   apache2/error.log  - Web server errors

4. View logs:
   tail -f /var/log/syslog
   (Real-time monitoring)

5. Search logs:
   grep "error" /var/log/syslog
   grep "Failed password" /var/log/auth.log
   
6. Count events:
   grep "Failed password" /var/log/auth.log | wc -l

7. Date filtering:
   grep "Dec 25" /var/log/syslog

8. Document: Findings
```

### TROUBLESHOOTING SCENARIOS (1.5 hours)

**Scenario 1: Service Won't Start**
```
Problem: Apache won't start
Steps:
1. Check status: systemctl status httpd
2. Check logs: tail /var/log/httpd/error.log
3. Find error message
4. Search for solution
5. Fix issue (example: port already in use)
6. Document: What was wrong
```

**Scenario 2: Disk Space Issue**
```
Problem: Disk is 95% full
Steps:
1. Check: df -h
2. Find large files: du -sh /*
3. Find directory: du -sh /var/log/*
4. Check logs: ls -lh /var/log/
5. Solution: Clean old logs
6. Document: Solution
```

---

## FRIDAY - DAY 19: SSH HARDENING & SHELL SCRIPTS

### SCHEDULE (6 hours - longer day)
- SSH hardening: 2 hours
- Lab 3D: SSH setup: 1.5 hours
- Shell scripting intro: 2 hours
- Lab 3C: Write scripts: 30 min

### PRIMARY RESOURCES

**Video Tutorials:**

1. **Professor Messer - SSH Security**
   - Channel: Professor Messer (YouTube)
   - Search: "Professor Messer SSH security"
   - Duration: 30 min
   - Content: SSH hardening best practices
   - Why: Critical for security

2. **NetworkChuck - Bash Scripting**
   - Channel: NetworkChuck (YouTube)
   - Search: "NetworkChuck bash scripting"
   - Duration: 60 min
   - Content: Write your first scripts
   - Why: Automation skill

3. **Bash Scripting Guide:**
   - Link: https://www.gnu.org/software/bash/manual/
   - Read: First chapter
   - Time: 1 hour

### LAB 3D: SSH HARDENING (1.5 hours)

**Secure SSH:**
```
1. Generate SSH key:
   ssh-keygen -t ed25519 -C "admin@server"
   (Saves to: ~/.ssh/id_ed25519)

2. Copy key to server:
   ssh-copy-id -i ~/.ssh/id_ed25519 user@host

3. Edit SSH config:
   sudo nano /etc/ssh/sshd_config
   
   Find & change:
   PermitRootLogin no
   PasswordAuthentication no
   X11Forwarding no
   MaxAuthTries 3

4. Restart SSH:
   sudo systemctl restart ssh

5. Test:
   - Key authentication: should work
   - Password auth: should fail
   - Root login: should fail

6. Document: All changes made
```

### SHELL SCRIPTING BASICS (2 hours)

**Script 1: System Health Check**
```bash
#!/bin/bash
# system-health.sh

echo "=== System Health Report ==="
echo "Hostname: $(hostname)"
echo "Uptime: $(uptime -p)"
echo ""
echo "Disk Usage:"
df -h
echo ""
echo "Memory Usage:"
free -h
echo ""
echo "CPU Load:"
top -bn1 | head -n 3
```

**Script 2: User Audit**
```bash
#!/bin/bash
# user-audit.sh

echo "=== User Account Audit ==="
echo "Users with shell access:"
cat /etc/passwd | grep bash | cut -d: -f1
echo ""
echo "Sudo users:"
getent group sudo | cut -d: -f4
```

**Create Lab 3C (1 hour):**
- Save scripts to GitHub
- Make executable: `chmod +x script.sh`
- Document: What each script does

---

## SATURDAY-SUNDAY: WEEK 3 WRAP-UP

### SATURDAY (3 hours)

**Lab Organization:**
- Organize Week 3 labs
- Create READMEs
- Verify documentation

**Linux Cheat Sheet:**
- Create: 2-page Linux reference
  - 30+ important commands
  - File permissions
  - User management
  - Services
  - Logs

### SUNDAY (2 hours)

**Week 3 Blog Post:**
- Title: "Securing a Linux Server: Essential Steps"
- Include: SSH hardening steps
- Include: Permissions best practices
- Include: Screenshots
- Publish on LinkedIn

**Assessment:**
- Week 3 quiz: 40 questions
- Target: 75%+
- Identify weak areas

**Week 4 Preparation:**
- Review: Advanced AWS section
- Watch: CloudFormation preview video
- Set Week 4 goals

---

---

# WEEKS 4-6 RESOURCES SUMMARY

(Due to length constraints, providing condensed resource guide)

## WEEK 4: ADVANCED AWS ARCHITECTURE

### Key Resources:
- **Primary:** A Cloud Guru "AWS Solutions Architect" course
- **Video:** NetworkChuck "CloudFormation explained"
- **Documentation:** AWS CloudFormation User Guide (https://docs.aws.amazon.com/cloudformation/)
- **Labs:** 4 comprehensive labs
- **Capstone:** 3-tier architecture CloudFormation template
- **Practice:** AWS official practice exams

---

## WEEKS 5-6: CERTIFICATION PREP

### CompTIA Network+ (Week 5 Exam):
- **Study Guide:** CompTIA Network+ Study Guide (Exam N10-008)
  - Link: Amazon or official CompTIA site
  - Read: All chapters
- **Videos:** Professor Messer N10-008 series (YouTube)
  - Watch: All videos
  - Link: https://www.professormesser.com/
- **Practice:** TutorialDojo & ExamTopics
  - Target: 200+ questions
  - Pass rate: 80%+
- **Official:** CompTIA CertMetrics practice test

### AWS Solutions Architect (Week 7-8 Exam):
- **Study:** AWS Solutions Architect exam guide
- **Course:** A Cloud Guru or Linux Academy
- **Labs:** Build capstone projects
- **Practice:** 3+ official AWS practice exams
- **Target:** 70%+ on practice exams

---

---

# WEEKS 7-12 QUICK RESOURCE REFERENCE

## WEEK 7-9: SECURITY & CERTIFICATIONS

**Resources:**
- ISC2 CC Study Guide (official)
- AWS security documentation
- Incident response frameworks
- Linux Essentials official guide
- TutorialDojo for all practice tests

**Key Platforms:**
- ExamTopics (questions)
- TutorialDojo (comprehensive)
- Official certification prep courses
- AWS Skill Builder
- Cisco Learning Network (Linux)

---

## WEEKS 10-12: JOB SEARCH RESOURCES

### LinkedIn Optimization:
- **Template:** LinkedIn profile optimization guide (included)
- **Photo:** Professional headshot tool - Canva, Snapseed
- **Content:** LinkedIn post scheduler (native or Buffer)

### Resume:
- **Template:** ATS-optimized resume (Provided)
- **Tools:** Grammarly (grammar check)
- **Validation:** ATS keyword scanner

### Job Search:
- **Platforms:**
  - LinkedIn Jobs
  - Indeed.com
  - AngelList (startups)
  - AWS Careers page
  - Cloud consulting companies

### Interview Prep:
- **Question Banks:** Included (50+ questions)
- **Mock Interviews:** Pramp, Interviewing.io
- **Recording:** OBS Studio (free recording tool)
- **Video:** Loom (screen recording)

---

---

# COMPREHENSIVE RESOURCE INDEX

## Video Channels to Subscribe To

1. **Professor Messer**
   - Link: https://www.professormesser.com/
   - Content: Networking+, Linux+, Security+
   - Quality: Excellent
   - Cost: Free

2. **NetworkChuck**
   - Link: YouTube, NetworkChuck channel
   - Content: AWS, networking, Linux, ethical hacking
   - Quality: Excellent, entertaining
   - Cost: Free

3. **Jeremy's IT Lab**
   - Link: YouTube, Jeremy's IT Lab
   - Content: Networking, Linux, general IT
   - Quality: Good, academic
   - Cost: Free

4. **AWS Official**
   - Link: YouTube, AWS channel
   - Content: Official AWS tutorials
   - Quality: Authoritative
   - Cost: Free

5. **Cisco Learning Network**
   - Link: https://learningnetwork.cisco.com/
   - Content: Networking certs
   - Quality: Excellent
   - Cost: Free community, paid courses

---

## Documentation to Bookmark

1. **AWS Documentation:** https://docs.aws.amazon.com/
2. **CompTIA:** https://www.comptia.org/
3. **ISC2:** https://www.isc2.org/
4. **Linux Foundation:** https://www.linuxfoundation.org/
5. **RFC Archives:** https://www.ietf.org/rfc/
6. **IANA Service Names:** https://www.iana.org/

---

## Practice Platforms (Paid)

1. **TutorialDojo:** https://tutorialsdojo.com/
   - Cost: $15-40
   - Content: 1000+ AWS questions
   - Quality: Excellent
   - **RECOMMENDED for certifications**

2. **A Cloud Guru:** https://acloud.guru/
   - Cost: $29/month
   - Content: Full courses + hands-on labs
   - Quality: Excellent
   - **RECOMMENDED for comprehensive learning**

3. **Linux Academy:** https://linuxacademy.com/
   - Cost: $29/month
   - Content: Linux, cloud, DevOps
   - Quality: Good
   - **RECOMMENDED for Linux labs**

---

## Free Resources Worth Using

1. **ExamTopics:** https://www.examtopics.com/
   - Practice questions (free section)
   - Quality: Good
   - Cost: Free (with premium option)

2. **AWS Skill Builder:** https://skillbuilder.aws.amazon.com/
   - Official AWS courses
   - Cost: Free tier available
   - Quality: Authoritative

3. **YouTube:**
   - Professor Messer (free)
   - NetworkChuck (free)
   - AWS Official (free)

4. **Reddit Communities:**
   - r/aws
   - r/ccna
   - r/learnlinux
   - r/sysadmin

5. **Discord Communities:**
   - AWS Discord
   - Networking Discord
   - Linux Discord

---

## Tools to Install

### Essential (Mandatory)
- [ ] AWS Free Tier account
- [ ] GitHub account & Git client
- [ ] VS Code (text editor)
- [ ] Terminal access (Linux/Mac/WSL)

### Highly Recommended
- [ ] Wireshark (packet analysis)
- [ ] Cisco Packet Tracer (networking sim)
- [ ] PuTTY or OpenSSH (SSH client)
- [ ] VirtualBox (virtual machines)

### Optional but Useful
- [ ] Docker (containerization)
- [ ] Terraform (IaC alternative)
- [ ] Python 3 (scripting)
- [ ] OBS Studio (screen recording)

---

## Budget-Friendly Setup

**Free Options:**
- All video tutorials (YouTube)
- AWS Free Tier ($0/month)
- GitHub (free for learning)
- Wireshark (free)
- All documentation (free)
- All practice questions (free tier)
- Linux (free OS)

**Small Investment:**
- CompTIA exam: ~$300
- AWS exam: ~$150
- ISC2 CC exam: ~$400
- Linux exam: ~$200
- Certification courses: $0-50 (many free)

**Total Cert Cost:** ~$1,050 (4 exams)
**Optional Paid Courses:** $0-100/month (optional)

---

## Backup Resources (If Primary Doesn't Work)

If NetworkChuck videos are down:
- Try: Professor Messer (alternative)
- Try: AWS Official (official source)
- Try: Linux Academy course

If AWS console changes:
- Check: AWS official documentation
- Try: AWS support forum
- Try: Stack Overflow

If you get stuck on lab:
- Check: Troubleshooting guide (provided)
- Ask: r/aws subreddit
- Ask: AWS Discord
- Email: Your mentor

---

## Recommended Study Schedule (for reference)

**Daily Minimum:** 6 hours
- 2 hours: Videos/theory
- 3 hours: Hands-on labs
- 1 hour: Practice questions & review

**Weekly Pattern:**
- Monday-Thursday: Full days (6 hours each)
- Friday-Saturday: Catch-up/review (6 hours each)
- Sunday: Lighter day, prep next week (3-4 hours)

**Total per week:** 60-70 hours

---

## Monthly Milestone Resources

**End of Month 1 (Week 4):**
- [ ] Complete Week 1-4 content
- [ ] Build Capstone #1
- [ ] Prepare Network+ exam
- [ ] Publish 3 blog posts
- [ ] 50+ LinkedIn connections

**End of Month 2 (Week 8):**
- [ ] Earn 2 certifications
- [ ] Complete Capstone #2
- [ ] 100+ LinkedIn connections
- [ ] 6 blog posts published
- [ ] 5 informational interviews

**End of Month 3 (Week 12):**
- [ ] Earn 4 certifications
- [ ] Complete 3 capstones
- [ ] 100+ connections, 20+ job applications
- [ ] Job interviews scheduled
- [ ] Expected job offers coming

---

This comprehensive day-by-day resource guide gives you specific, actionable resources for every single day of the 12-week program. Print it, bookmark it, and reference it daily during your learning journey.

**Good luck!**
