# adweeknyc2025-hackathon
Dataset and Videos for Adweek NYC 2025 Hackathon Challenge

This repo contains the video files, quantitative results and qualitative feedback for the following RCT experiments for creative pre-testing on Swayable:

Quantitative results for each experiment are included in .csv format, identified by "Results" in the filename.
Qualitative feedback is included in.csv format, identified by "Comments" in the filename.

## Data dictionary (Results):
- metric: The metric on which the impact was measured
- segment: Name of the segment
- breakdown: The dimension along which the population is segmented. For example, "Male" and "Female" would be segments in the "Gender" breakdown
- filter: This is a segment that is used to filter the data for this row of results, cross-tabulating with the segment column. 
- delta: Mean treatment effect (testGroupMean minus baselineMean)
- marginOfError: Margin of Error on each side of the treatment effect, forming the Confidence Interval (CI) around the treatment effect
- ci_70_interval: 70% confidence interval around the treatment effect
- ci_80_interval: 80% confidence interval around the treatment effect
- ci_90_interval: 90% confidence interval around the treatment effect
- ci_95_interval: 95% confidence interval around the treatment effect
- baselineSampleSize: Sample size of the treatment/segment/filter combination in the control group
- testGroupSampleSize: Sample size of the treatment/segment/filter combination in the test group
- effectiveSampleSize: Weight of the segment in the overall population. Used to determine how valuable the impact on this segment is relative to other segments
- totalWeight: Weight of the segment in the overall population. Used to determine how valuable the impact on this segment is relative to other segments
- pvalue: p-value
- treatment: Name of the treatment stimulus. Also known as "content"
- baselineMean: Mean value of the metric in the control group 
- testGroupMean: Mean value of the metric in the test group

### Ignore the following fields 
- effectiveSampleSize
- pvalue

## Data dictionary (Comments / Qualitative Responses)
The "comments" CSVs contain qualitative, open-ended survey responses along with segmentation info. 

Each row in the comments dataset represent one survey respondent. The dataset is structured into three main groups of columns, roughly in this order:

1. **Respondent Metadata**  
   - `response_id` – Unique ID for the respondent  
   - `weight` – Statistical weight assigned to this respondent after population balancing (ignore this, it's not expected to be useful for this challenge)

2. **Segment Flags**  
   A large block of columns representing **binary membership indicators** for audience segments. Each column corresponds to a specific segment, and values indicate whether the respondent belongs to that segment:
   - `TRUE` or `1` → respondent **belongs to** this segment  
   - `FALSE`, `0` or blank → respondent **does not belong to** this segment  

   Examples of segment columns:
   - `age_18_24`
   - `uses_instagram`
   - `drinks_sparkling_water`
   
   These segment columns are designed to enable **cross-tabulation, filtering, and group-level analysis**.

3. **Qualitative Response Fields**  
   One or more columns at the end of the dataset contain the **open-ended textual answers** to survey questions. Each column corresponds to a single qualitative question.

   At the end there are columns that contain the open-end responses. If there are multiple questions in the dataset, each question has its own column, containing the corresponding responses. These fields typically contain free-form text and should be treated as **unstructured data** suitable for NLP pipelines, clustering, topic modeling, sentiment analysis, etc.

### 🧪 Example Row Structure

| respondent_id | age_18_24 | drinks_sparkling_water | uses_instagram | open_end_question                                                            |
|---------------|-----------|------------------------|----------------|------------------------------------------------------------------------------|
| 12345         | TRUE      | TRUE                   | FALSE          | "I love how this brand feels more environmentally responsible than others."  |
| 12346         | FALSE     | FALSE                  | TRUE           | "The ad didn’t resonate with me — it felt too corporate and not authentic."  |

### 🔧 Notes
- **Segment columns are dynamic:** The set and order of segment columns may vary between surveys, depending on the segmentation scheme used. Do not hardcode column positions; instead, programmatically detect segment columns based on known metadata fields and qualitative column names.
- **Qualitative columns are free text:** Expect variability, typos, and mixed formatting. 
- **Binary values:** Segment membership columns may appear as `1/0`, `TRUE/FALSE`, or non-empty/empty. Standardize to boolean for downstream use.

## Additional resources:
RCT methodology: 
Swayable blog: https://insights.swayable.com

## Contact
Reach out to anshuk@swayable.com for any questions about the dataset
