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


## Additional resources:
RCT methodology: 
Swayable blog: https://insights.swayable.com

## Contact
Reach out to anshuk@swayable.com for any questions about the dataset