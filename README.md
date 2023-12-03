**Potential Talents - Project-**

This project aims to automate the talent sourcing and management process for a talent sourcing company. The goal is to develop a machine learning-powered pipeline that can identify and rank potential candidates based on their fitness for specific roles. The pipeline includes keyword-based candidate search, candidate ranking, manual review, and candidate re-ranking based on supervisory signals.

**Background:**

As a talent sourcing and management company, the process of finding talented individuals for technology companies is challenging due to the need to understand the client's requirements and the qualities that make a candidate shine in a particular role. Additionally, identifying where to find talented individuals poses another challenge. The current process involves manual operations, and the company wants to automate and optimize this process to save time and identify the best-fit candidates efficiently.

**Data Description:**

The data used in this project comes from the company's sourcing efforts. Personal details have been removed, and each candidate is assigned a unique identifier. The attributes of the candidate data include:

* id: Unique identifier for the candidate (numeric)
* job_title: Job title for the candidate (text)
* location: Geographical location of the candidate (text)
* connections: Number of connections the candidate has (text)
* fit: Target variable indicating how fit the candidate is for the role (numeric, probability between 0 and 1)
Output (desired target)
* Keywords: "Aspiring human resources" or "seeking human resources"
**Goal(s):**
Predict how fit the candidate is based on their available information (variable fit)

**Success Metric(s):**

Rank candidates based on a fitness score

Re-rank candidates when a candidate is starred
