# Potential Talent (NLP)

# Background:

Our objective is to enhance the efficiency of talent sourcing and management company by developing an intelligent system that utilizes machine learning to identify and rank potential candidates based on their fitness for specific roles. Additionally, we seek to incorporate a supervisory signal in the form of candidate starring during the manual review process, allowing for the re-ranking of candidate lists based on valuable feedback from the selection team.

Ultimately, our goal is to reduce manual efforts and human bias, save time, and optimize the talent acquisition process.

# Data Description

Data comes from the company sourcing efforts; it contains text attributes from the candidate profiles. The dataset has undergone careful data cleaning to protect personal information. Each candidate is represented by a unique identifier and several attributes.

## Attributes (Features):

id: A unique numerical identifier for each candidate.
job_title: The job title associated with the candidate.
location: The geographical location of the candidate.
connections: The number of connections a candidate has, where "500+" implies more than 500 connections.

## utput (Label):
* fit: This numeric value represents how suitable a candidate is for a specific role, ranging from 0 to 1.

# Goal(s):

* Our primary goal is to predict the fitness of a candidate for a particular role, as represented by the fit variable.
* Success Metric(s): 1) Rank Candidates: Rank candidates based on a fitness score, making it easier to identify the most suitable candidates. 2) Re-rank Candidates: Re-rank candidates when a candidate is "starred" to account for new information or actions.

# Bonus(es)

* Filtering Candidates: Efficiently filter out candidates who should not be on this list in the first place.
* Universal Cut-off Point: Determine a cut-off point that works effectively for various roles without excluding high-potential candidates.
* Bias Mitigation: Develop automated procedures to reduce human bias in the candidate selection process.
(Our objective is to build a robust algorithm that not only predicts candidate fitness but also adapts to changes and promotes fairness and efficiency in the selection process.)





