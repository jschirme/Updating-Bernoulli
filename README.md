# INTRODUCTION

These are the data and anaysis files used in my master's thesis (https://uwspace.uwaterloo.ca/items/28dffc4a-4a74-4772-92a0-9e0a5fd059e0), and for a manuscript submitted to Psychonomic Bulletin and Review (PBR).

## ORGANIZATION
- The raw manuscript (PBR_manuscript.Rnw) is provided as an Rnw/Sweave file that can be recompiled into a LaTeX file or a pdf file.
  - This raw manuscript contains the main text for the manuscript as well as embedded codeblocks for all the computed analyses in R.
- Supplementary material (such as plots) is provided in the Folder 'Supplementary'
- The main analyses in R are below and numbered (1a, 1b and 2).
  - They are arranged in order of presentation in the manuscript. They rely on additional code provided in the subdirectory 'supporting'.


# ANALYSES
## File Organization 
There are three analysis files. In the order they appear in the manuscript:
### 1a.group-level-analyses
- t-test that establishes manual participants make more adjustments
- violin plot showing the participant distribution over number adjustments
- t-test that establishes manual participants make a higher proportion negative adjustments
- t-test that establishes manual participants 'added adjustments' are positively biased
### 1b.fitting-models
- model fitting procedure
- testing AIC differences
- plotting models
### 1c.individual-ppt-analyses
- function plotting individual participants' behavior over the course of the task

## Data frame Organization
There are two data frame formats: 'standard' and 'by adjustments' 
- the standard data frames have 1 row per trial
	- per trial it includes: the dot colour, a participant's bernoulli estimate, the true bernoulli parameter, etc
	- the two standard data frames are "task_df" which contains only un-excluded participants, and "r_df" which includes every participant
- the 'by adjustments' data frames have 1 row per adjustment size
	- 'AdjSize' column: adjustment sizes range from -100 to 100, where negative is 'sample inconsistent adjustment' and positive is a 'sample consistent adjustment' (according to the most recent dot colour)
	- 'NumAdjs' column: number of adjustments is that number of adjustments per each sample size

# DATA FILE COLUMNS
Each row in this data file corresponds to one slide of the experiment. Some of these are instruction screens; some are survey questions; and some are trials of the task.
## Highlighted Columns:
- PptId: Participant ID
- Condition: Experimental group: "Manual" or "Automatic"
- SlideClass: "Trial" for trial of the task
- SlideType: "Practice" for practice trial, "Task" for experimental trial, "Demo" for single demo slide during instructions
- BlockNum: block number (1,2,3)
- TrialNum: trial number (1-999)
- TrialRingCol: colour of the dot
- TrialRingBoolean: boolean of the dot colour (blue = 0; red = 1)
- bernoulliEstimate: one the 100-setting slider, a value between 0-1 for proportion red dots
- TrueBernoulliParam: actual Bernoulli parameter (probability of a red dot)