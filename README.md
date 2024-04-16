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

## Output (Label):
* fit: This numeric value represents how suitable a candidate is for a specific role, ranging from 0 to 1.

# Goal(s):

* Our primary goal is to predict the fitness of a candidate for a particular role, as represented by the fit variable.
* Success Metric(s): 1) Rank Candidates: Rank candidates based on a fitness score, making it easier to identify the most suitable candidates. 2) Re-rank Candidates: Re-rank candidates when a candidate is "starred" to account for new information or actions.

# Bonus(es)

* Filtering Candidates: Efficiently filter out candidates who should not be on this list in the first place.
* Universal Cut-off Point: Determine a cut-off point that works effectively for various roles without excluding high-potential candidates.
* Bias Mitigation: Develop automated procedures to reduce human bias in the candidate selection process.
  
(Our objective is to build a robust algorithm that not only predicts candidate fitness but also adapts to changes and promotes fairness and efficiency in the selection process.)

# Solution:

## Data Preprocessing:

As you can see, the data contains symbols, duplicates and acronyms. We need to preprocess them first. Using custom functions and regular expressions, we have enabled data preprocessing.

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/0c1e8102-c30c-49eb-aa86-c4500d5dce4b)

The plot below illustrates the word frequency, presented in the sorted list below, allowing for a better understanding.

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/1a57dcc5-2672-4047-816c-a06e8cde9360)

We are seeking candidates who show interest in human resources, which can be identified through the presence of keywords such as "Aspiring human resources" or "Seeking human resources". Therefore, we will use either of these phrases as our search keyword.

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/c1a6bb95-61c2-4e2c-ba3c-341106bc73be)

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/a89b7536-dc54-4631-89f0-14fa01fa271b)


To optimize the fitness score, we can combined all the individual fit scores through feature engineering for a comprehensive evaluation of candidate suitability. We can also employe a weighted sum approach to create a final fit score, considering the significance of each candidate's connections.

# Ranking candidates:

* We incorporated a weighted fit score, utilizing the scaled connection count along with text relevance from multiple fit scores. Given the crucial role of connections in recruitment positions, this approach assigns significant importance to connection count in HR job roles. The weighted combination of fitness scores and scaled connection count aims to strike a balance between the influence of connections and title semantics.
  
* To enhance the effectiveness of the ranking solution, a cut-off threshold has been implemented to eliminate non-relevant candidates. The current threshold has been fine-tuned to align with the characteristics of the current dataset. It ensures a fair trade-off between title semantics and the networking skills of candidates.

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/23f2f05d-0851-4d54-a638-7f7b1b1ed7ab) 

# Reranking candidates:


* Finally reranking by starring ideal candidates helps surface other potentials similar to that profile, this refines the ranking further using the starred candiate attributes as a baseline.
  
* Encoded additional attributes like location and fitscore to better match candidates.

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/eed1b269-30d3-47d8-9968-4b06fafd5153)
  
# Job titles ranking

![image](https://github.com/53KIbGcAqz0Gokmj/t0OXVwqXusxsX8RM/assets/143815258/aef8036a-731a-42f0-8ba6-cc1b1f55ef6a)

# BONUS : Rank prediction using LGBMRanker

* The proposed solution utilizes a LambdaRank model, which is a learning-to-rank algorithm based on gradient boosting with LightGBM. The algorithm is trained to optimize the ranking of candidates based on their relevance scores (ranking_SBERT_binary) and similarity scores (similarities_SBERT).

# Final Observation:  

This solution not only predicts candidate fitness but also adapts to changes, promoting fairness and efficiency in the selection process.

* Leveraging various encoders, we effectively capture relevant semantics from job titles.
* Through feature engineering, the fitness score of candidates is refined by incorporating a weighted combination of semantics from titles and scaled communication (representing networking skills), ensuring a fair ranking system.
* The implemented threshold guarantees the retention of only relevant candidates, allowing the algorithm to further refine the ranking effectively.
* Continuous refinement of the ranking occurs with every starring action, making the search baseline more relevant with each human input. Advanced NLP embedding techniques aid in surfacing similar candidates, ensuring fairness without bias, and the LGBMRanker with a linear kernel reinforces this process.
* To enhance the solution's performance, fine-tuning the weighted sum of the feature-engineered fit score and adjusting the cutoff threshold is recommended. This refinement process can be further improved by accessing additional candidate data.
* In a broader context, the solution is adaptable to other job roles by modifying keywords and making minor adjustments in text preprocessing. It's crucial to note that the current feature-engineered score and cutoff are customized for the HR role.
