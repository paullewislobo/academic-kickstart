+++
title = "10k Preprocessing"
date = 2019-01-25T21:40:38-06:00
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = []

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []
categories = []

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
# projects = ["internal-project"]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

# 10K Pre processing

## This repository is being used to help in pre processing the 10K dataset so that it can be used for various analysis.
## See the Setup.md file for instructions on how to setup the environment and process the data.

#### 10K.py

- This file is used to read data from a mongo database collection and run 3 different analysis on it.
- Currently we are using the UBC 10K dataset that already has the individual items extracted from the original 10K reports.
- setting.py can be configured to run the different reports.
    - COMMON_WORDS is a report that contains the 10 most significant changes in words for each company between each consecutive year.
    - JACCARD will generate a report for the JACCARD coefficient for each company between each consecutive year.
    - IMP_PHRASE will generate a report for the change in the given phrases for each company between each consecutive year.
    
#### gen_report.py

- Generates excel files for the IMP_PHRASE report for each Phrase provided in the input.

#### impphrase.py

- Generates a word2vec model that is trained on the entire 10K dataset. Using it we can generate similar phrases from the initial seed phrases
  used in the IMP_PHRASE report.
