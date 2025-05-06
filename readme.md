# Job Seeker Data Pipeline

## Overview
The Job Seeker Data Pipeline is the backbone of our AI-powered job search engine for the Australian market. Traditional job search platforms offer generic recommendations based solely on rule-based matching. Our pipeline addresses this by collecting both explicit inputs (via tailored surveys) and implicit signals (via A/B job comparisons), then processing and transforming raw job data into meaningful features that drive personalized recommendations.

## Key Features
- **Comprehensive Data Collection:** Retrieves job listings from external APIs (e.g., Seek) and company details via LinkedIn.
- **User Input Integration:** Ingests detailed user profiles and survey responses to capture explicit preferences.
- **Advanced Feature Engineering:** 
  - Converts raw salary descriptions into normalized annual salary values.
  - Normalizes job location data using an Australian postcode dataset and computes distances with the Haversine formula.
  - Uses NLP (e.g., SentenceTransformer) to compute similarity scores between job descriptions, titles, and user resumes.
- **Data Preprocessing:** Cleans and transforms disparate data formats to create a unified dataset for ranking.
- **Scalability:** Designed to handle and process large volumes of job and user data efficiently.

## Methodology
1. **Data Ingestion:** 
   - Collect job data using Seek APIs.
   - Retrieve supplementary company data via LinkedIn APIs.
2. **Data Transformation:**
   - Convert salary texts into standardized numerical values.
   - Transform location strings into coordinates for distance calculations.
   - Compute similarity scores for job titles, descriptions, and industry relevance.
3. **Feature Engineering:**
   - Create both numerical features (e.g., normalized salary, distance) and categorical flags (e.g., work-from-home indicators).
   - Aggregate these features to form a comprehensive profile for each job.
4. **Output:** 
   - The resulting processed dataset is used downstream for machine learning model training and ranking in the microservice.

## Job Seeker Video Demonstration

<a href="https://img.youtube.com/vi/AqKWgewsZsU" target="_blank">
  <img src="https://img.youtube.com/vi/AqKWgewsZsU/0.jpg" width="650"/>
</a>

##  Notebook
The majority of code and analyses are documented in the Jupyter Notebook:
<a href="https://github.com/HENRYCCHH/Job_Seeker_Data_Pipeline/blob/main/job_seeker_model_v10.ipynb" target="_blank">
  <code>job_seeker_model_v10.ipynb</code>
</a>
