# System Health & Security Audit Bash Script

## Introduction

This project is a beginner-friendly Bash scripting assignment designed to solidify your understanding of the fundamentals of Linux system administration, automation, and basic security monitoring.

In real-world IT roles, coding tasks often come with vague or incomplete instructions, and as a result, you’re expected to figure out what needs to be done, clarify requirements when needed, and make logical decisions based on your understanding of the goal. For example...

Imagine that you’ve just been hired as a junior Linux admin at a IT Support company. One of your first assignments is to help automate part of their internal auditing process. The lead sysadmin wants you to write a script that will run a basic health and security audit on any Linux machine. You are told: “We need something simple that gives us a snapshot of a system’s status. It should check basic info, look for warning signs, and create a clean report we can review or save for later.”

That’s it. No other context. Nevertheless, your job is to write a script that fulfills this request based on your best assumptions.

This project is meant to showcase that most real-world requests will not come with step-by-step instructions. And you’ll often need to identify missing details, decide on the best approach, and communicate your solution effectively.

## Instructions

In this project, you'll develop a script that performs a system health and security audit on a Linux machine. You'll gather important system information, monitor resource usage, analyze logs for suspicious activity, and output a clear, timestamped report. 

To accomplish this task, you will:

1. Login to your Ubuntu VM and open your bash project script file within VS Code.
2. Develop a bash script that executes a routine system check using the specifications below and outputs a simple report based on the information gathered.
3. Conduct a self evaluation of your script and your report, using the criteria below.
4. Submit the link to your public repo.
5. Once submitted you will be able to conduct a peer code review, evaluating your peer's script based off the criteria below.
6. Once your peer has completed their code review, compare your self-evaluation with your peer's review.



## What the Script Should Do

- [ ] Collect and display system information: hostname, IP address, uptime, and kernel version.
- [ ] Check and display disk usage; alert if usage exceeds a defined threshold.
- [ ] List currently logged-in users and identify accounts with potential security risks (e.g., empty passwords).
- [ ] Analyze system processes and highlight top memory consumers.
- [ ] Verify that essential services are running: `systemd`, `auditd`, `cron`, `systemd-journald`, and `ufw`.
- [ ] Parse recent authentication logs to find failed login attempts.
- [ ] Save all output to a **timestamped report** saved to the user's desktop.

> 💡 Remember: You could use AI to complete this task, but you won’t have AI to help you in your interview.



## Deliverables

Submit the link to your public GitHub repository.


## Bash Script Evaluation Criteria

### 1. Script Functionality (10 Points)
- **1–3:** Script is broken or doesn’t run properly, and looks rushed or thrown together.
- **4–6:** Script performs the main task but may fail in edge scenarios or lacks polish.
- **7–8:** Script reliably completes its task; minor inefficiencies exist.
- **9:** Solid script; handles different inputs robustly.
- **10:** Includes usage instructions, optional flags, logging, or permission checks.

### 2. Script Readability & Structure (10 Points)
- **1–3:** Messy, no indentation, unclear flow or confusing variables.
- **4–6:** Basic formatting and naming; moderately easy to follow.
- **7–8:** Clear structure, readable code, descriptive variable names.
- **9–10:** Professional formatting, consistent style, easy to follow.

### 3. Script Uses Bash Best Practices (10 Points)
- **1–3:** Poor practices (unquoted variables, backticks, etc.).
- **4–6:** Some good practices; several oversights.
- **7–8:** Proper quoting, effective command usage.
- **9–10:** Excellent use of Bash conventions, secure scripting habits.

### 4. Script Error Handling (10 Points)
- **1–3:** No validation or error checks.
- **4–6:** Basic validation present.
- **7–8:** Anticipates common issues; provides useful feedback.
- **9–10:** Robust checks, helpful error messages, graceful failures.

### 5. Script Modularity & Usability (10 Points)
- **1–3:** Hardcoded values, no reuse.
- **4–6:** Basic adaptability through variables or arguments.
- **7–8:** Uses functions or parameters for adaptability.
- **9–10:** Modular and reusable design; user-friendly.



## Interpretation Scale for Self Evaluation

Total your score from all 5 metrics. Use the chart below to interpret your results:

| **Total Score Range** | **Score Meaning**                                                   |
|------------------------|---------------------------------------------------------------------|
| 5–20 ❌                | Rejected – Script lacks functional and professional fundamentals.   |
| 21–30 ⚠️              | Weak Candidate – Shows potential but needs mentoring.               |
| 31–40 ✅              | Interview Recommended – Strong foundational knowledge.              |
| 41–50 ⭐              | Hire/Top-Tier – Ready for entry-level sysadmin work.                |
