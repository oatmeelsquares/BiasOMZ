# BiasOMZ
Project materials for DS 6015: DS Capstone as part of UVA School of Data Science Master's in Data Science. The goal of this project is to evaluate a model from Intel's [Open Model Zoo](https://github.com/openvinotoolkit/open_model_zoo/tree/master) for potential bias against protected characteristic(s). 

# Potential datasets:
Audio:
- https://www.kaggle.com/datasets/mohammedabdeldayem/the-fake-or-real-dataset |  195k recordings but some are from AI
- https://data.mendeley.com/datasets/4gzzc9k49n/4 |  7637 audio files totalling more than 9.5 recording hours (presumed all female voices)
- https://www.kaggle.com/datasets/subhajournal/patient-health-detection-using-vocal-audio | speech from people with and without vocal diseases

Images:
- https://scikit-image.org/ | A Python package with image library 
- https://www.kaggle.com/datasets?search=image | 26,990 image datasets including 274 NLP datasets 
- https://research.google/blog/introducing-the-open-images-dataset/?m=1 | Links to popular image libraries like [ImageNet](https://image-net.org/) and  [YFCC100M](https://webscope.sandbox.yahoo.com/catalog.php?datatype=i&did=67&guccounter=1)

# Final deliverable:
A written report with:
- literature review including what techniques currently exist for detecting bias, their strengths and limitations
- Description of the data & how we found it
- Description of the model and what metric(s) we used to evaluate it, based on the lit review
- Results of evaluation
- Conclusion: does the model show bias or not?
- Potential: description of an established pipeline OR recommendations for evaluating future models

A presentation with:
- what we found in our lit review and why we chose the metrics we did
- Description of the model we chose and why we chose it
- Description of the process of getting the data, accessing the model, and evaluating it
- What we found - performance on bias metrics
- Conclusion: biased or not?
- Potential: description of an established pipeline OR recommendations for evaluating future models

# Project roadmap

Week 1 (Jan 17-23):
- Determine final deliverable
- Set out project roadmap (this)
- Email sponsors with project plan and roadmap

Weeks 2-4 (Jan 24 - Feb 6):
- Dig into researching bias in AI and possible metrics
- Add notes to the issue

Week 5: (Feb 7-13):
- Tentatively decide on what metrics and model to use
- Find datasets to test on

Week 6: (Feb 14-20)
- Finalize decision on what metrics, model, and dataset(s) to use
- DETAILED documentation of decision and reasoning
- Begin writeup of the previous

Week 7: (Feb 21-27)
- Finalize writeup of Report 1

**Feb 27: Report 1 DUE**

Week 8: (Feb 28 - Mar 6)
- Get data into (jupyter) environment

Week 9-11: (Mar 7-27)
- Spring break
- Implement tests, evaluate model
- DETAILED documentation of findings

Week 12: (Mar 28 - Apr 3)
- * Flex week - extra time for implementing tests/evaluating model if things go wrong, or starting to establish the bias eval pipeline
- Begin writeup of report 2: what we have accomplished so far and plan for pipeline
- May begin work on the pipeline in this week

Week 13-14: (Apr 4-16)
- Write/finalize report 2
- Start on pipeline in earnest
- DETAILED documentation of pipeline

**Apr 17: Report 2 DUE**

Week 15: (Apr 17-23)
- Finalize pipeline
- DETAILED documentation of pipeline
- Start final report writeup

Week 16: (Apr 24-30)
- No more technical work (it is what it is)
- Final report
- Final presentation

**May 1: Final Deliverables DUE**
