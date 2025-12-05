# Coordinated Amplification and Misinformation Detection in Global YouTube Conflict Narratives

[![Course](https://img.shields.io/badge/Course-CS%20418-blue)](https://github.com/Archit1706/cs418-project)
[![Team](https://img.shields.io/badge/Team-The%20Fact%20Finders-green)](https://github.com/Archit1706/cs418-project)
[![Fall 2025](https://img.shields.io/badge/Semester-Fall%202025-orange)](https://github.com/Archit1706/cs418-project)
[![Status](https://img.shields.io/badge/Status-Completed-success)](https://github.com/Archit1706/cs418-project)

> **Final Submission - December 8, 2025**

## 📋 Table of Contents
- [Overview](#overview)
- [Team Members](#team-members)
- [Problem Statement](#problem-statement)
- [Core Hypotheses](#core-hypotheses)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Key Results](#key-results)
- [Visualizations](#visualizations)
- [Project Structure](#project-structure)
- [Final Deliverables](#final-deliverables)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Reproducibility](#reproducibility)
- [Acknowledgments](#acknowledgments)

---

## 🎯 Overview

This project comprehensively maps the ecosystem of coordinated misinformation and narrative manipulation surrounding the Russia-Ukraine conflict on YouTube. By combining **Network Science**, **Anomaly Detection**, and **State-of-the-Art NLP techniques**, we analyzed over **5.9 million comments** across **440,000+ videos** from **1,561 channels** spanning 20 years (2005-2025).

### Why This Matters

- **Platform Integrity**: Essential for maintaining content health and preventing manipulation
- **Societal Impact**: Misinformation during conflict has real-world consequences, requiring automated detection tools
- **Scientific Novelty**: Combining multiple analytical approaches to study the full lifecycle of coordinated information campaigns

### Key Achievements ✅

- ✅ Validated all three research hypotheses with quantitative evidence
- ✅ Identified 17× increase in video production during 2022 conflict escalation
- ✅ Detected power law distribution: Top 1% of videos exceed 1M views
- ✅ Found News & Politics content has 3× higher engagement rates
- ✅ Discovered coordinated posting patterns (peak 12-6 PM UTC)
- ✅ Mapped network with 0.9843 modularity (excellent community structure)

---

## 👥 Team Members

| Name | UIC Email | GitHub | Role |
|------|-----------|--------|------|
| **Archit Rathod** | arath21@uic.edu | [@Archit1706](https://github.com/Archit1706) | Data Lead, Strategic Timing Analysis |
| **Srinath Ganesh** | sgane34@uic.edu | [@srinath-ganesh](https://github.com/srinath-ganesh) | Temporal Surge & Anomaly Detection |
| **Vishaal Dayashanker** | vdaya@uic.edu | [@VishaalD07](https://github.com/VishaalD07) | Power Law & Engagement Analysis |
| **Harsh Shelke** | hshel@uic.edu | [@harshelke180502](https://github.com/harshelke180502) | Channel Dominance & Network Structure |
| **Vignesh Pathak** | vpath6@uic.edu | [@VighneshDev1411](https://github.com/VighneshDev1411) | Controversy Detection & Comment Analysis |

**Course**: CS 418: Introduction to Data Science (Fall 2025)  
**Team Name**: The Fact Finders  
**Institution**: University of Illinois Chicago

---

## 🔍 Problem Statement

YouTube serves as a major conduit for viral, multilingual political narratives. This project aims to:

1. **Identify and characterize** coordinated methods used by channels and users to amplify specific narratives
2. **Detect** resulting inorganic engagement patterns through statistical anomaly detection
3. **Analyze** narrative evolution over time in correlation with real-world conflict events
4. **Quantify** the scale and structure of coordinated information campaigns

Our focus is on content related to the Russia-Ukraine conflict, analyzing narratives across Russian, Ukrainian, and English language content.

---

## 🔬 Core Hypotheses

### H1: Coordination ✅ VALIDATED
**Hypothesis**: Misinformation is amplified by highly interconnected "clusters" of channels and commenters.

**Evidence**:
- Network modularity: **0.9843** (excellent community structure)
- Top 10% of channels produce **50% of all content**
- Largest cluster: **1,374 highly connected nodes**
- Top single channel: **1,373 videos**

### H2: Anomalies ✅ VALIDATED
**Hypothesis**: Periods of intense real-world conflict correlate with statistically significant engagement anomalies.

**Evidence**:
- Clear spikes in 2014 (Crimea annexation) and 2022 (full invasion)
- **17× increase**: ~10,000 videos/year (2013) → **170,000+ videos (2022)**
- 20 significant anomalies detected via Isolation Forest
- Maximum Z-score: **37.06** (October 2009)

### H3: Evolution ✅ VALIDATED
**Hypothesis**: Narratives promoted by coordinated networks shift predictably over time.

**Evidence**:
- News & Politics content: **3× higher comment-to-view ratios**
- Strategic posting times: **12-6 PM UTC** (US/EU peak hours)
- Weekday posting bias: **Tuesday-Thursday peaks**
- 10 coherent topics tracked over time with clear temporal evolution

---

## 📊 Dataset

### Final Dataset Statistics

| Metric | Count | Details |
|--------|-------|---------|
| **Total Comments** | 5,940,182 | 5,938,888 unique |
| **Videos Analyzed** | 440,772 | Across 32 categories |
| **Channels** | 1,561 | Unique content creators |
| **Temporal Range** | 2005-2025 | 20 years of data |
| **Languages** | 3 | Russian, Ukrainian, English |
| **Missing Data** | <0.02% | High data quality |

### Data Sources

- **Primary**: YouTube Data API (v3) - Video metadata, comments, channel information
- **Supplementary**: FakeNewsNet, LIAR datasets for ML training
- **Storage**: Google Cloud BigQuery + Parquet files for efficient processing

### Data Access

📁 **Full Dataset**: [Google Drive](https://drive.google.com/drive/folders/1yT8_b9zMD02xL1yyDDLJn0iv2Hus8h5m?usp=sharing)
- Cleaned data in Parquet format
- Raw data available upon request
- Data collection scripts in `task1_data_collection_and_cleanup/`

---

## 🛠️ Methodology

### Analysis Pipeline

```
Data Collection → Cleaning & Preprocessing → Multi-Method Analysis → Validation
     ↓                    ↓                         ↓                    ↓
  YouTube API       Translation         Network Analysis        Hypothesis
  Async Requests    RU/UA/EN          Anomaly Detection         Testing
                    Standardization   Topic Modeling
```

### Techniques Used (20+ Methods)

| Analysis Type | Techniques | Key Findings |
|---------------|------------|--------------|
| **Temporal Analysis** | Time series, Z-score detection, Event correlation | 17× surge in 2022, clear conflict spikes |
| **Network Science** | PageRank, Louvain clustering, Modularity analysis | 0.9843 modularity, 315 communities |
| **Anomaly Detection** | Isolation Forest (n=200), Rolling windows, Statistical outliers | 20 major anomalies, max Z-score: 37.06 |
| **Engagement Analysis** | Power law fitting, Percentile analysis, Gini coefficient | Top 1% >1M views, bottom 50% <1K |
| **NLP & Topic Modeling** | BERTopic, Multilingual transformers, HDBSCAN | 10 topics, clear narrative evolution |

---

## 🎯 Key Results

### 1. Temporal Surge Analysis (Srinath Ganesh)

**Finding**: Channel creation and video publishing surged during major conflict events.

- **2014 Spike**: Crimea annexation triggered channel creation surge
- **2022 Peak**: Full invasion resulted in 170,000+ videos (17× baseline)
- **Correlation**: Statistical significance between real-world events and platform activity

📊 **Visualization**: [Channel Creation by Year](https://github.com/Archit1706/cs418-project/blob/master/plots/Channel%20Creation%20by%20Year.png)

---

### 2. Strategic Publishing Patterns (Archit Rathod)

**Finding**: Videos published during high-traffic hours suggest coordination.

- **Peak Hours**: 12-6 PM UTC (US/EU daytime)
- **Weekday Bias**: Tuesday-Thursday highest activity
- **Monthly Peaks**: October consistently elevated
- **Non-random distribution** indicates strategic timing vs. organic posting

📊 **Visualization**: [Video Creation by Time](https://github.com/Archit1706/cs418-project/blob/master/plots/Video%20Creation%20by%20Time.png)

---

### 3. Power Law Engagement Distribution (Vishaal Dayashanker)

**Finding**: Video engagement follows classic viral amplification pattern.

- **Top 1%**: Exceed 1,000,000 views each
- **Bottom 50%**: Fewer than 1,000 views
- **90th Percentile**: 875,313 views
- **Median**: Near 0 (large dormant content share)
- **Gini Coefficient**: ~0.85 (extreme inequality)

📊 **Visualization**: [View Analysis](https://github.com/Archit1706/cs418-project/blob/master/plots/View%20Analysis.png)

---

### 4. Channel Dominance (Harsh Shelke)

**Finding**: Small number of channels dominate content production.

- **Top 20 Channels**: 1,000+ videos each
- **Single Top Channel**: 1,373 videos
- **Concentration**: Top 10% produce 50% of all content
- **Evidence**: Suggests professional operations or automation

📊 **Visualization**: [Videos per Channel](https://github.com/Archit1706/cs418-project/blob/master/plots/Videos%20per%20Channel.png)

---

### 5. Controversy Indicator (Vignesh Pathak)

**Finding**: High comment-to-view ratios indicate controversial content.

- **Median Ratio**: 0.001 (1 comment per 1,000 views)
- **Top 5% Threshold**: >0.05 (high controversy marker)
- **News & Politics**: 3× higher engagement than average
- **Category Targeting**: Disproportionate focus on politically sensitive topics

📊 **Visualizations**: 
- [Comments vs Videos](https://github.com/Archit1706/cs418-project/blob/master/plots/Comments%20vs%20Videos.png)
- [Top Video Categories](https://github.com/Archit1706/cs418-project/blob/master/plots/Top%20Video%20Categories.png)

---

## 📈 Visualizations

All visualizations are available in the [`/plots`](https://github.com/Archit1706/cs418-project/tree/master/plots) directory.

### Key Figures

1. **Channel Creation by Year** - Temporal surge analysis showing 2014/2022 spikes
2. **Video Creation by Time** - Strategic posting patterns (12-6 PM UTC)
3. **View Analysis** - Power law distribution visualization
4. **Videos per Channel** - Channel dominance and concentration
5. **Comments vs Videos** - Engagement correlation analysis
6. **Top Video Categories** - Category distribution and targeting

### Interactive Visualizations

- Network graphs with community detection
- Topic evolution over time (BERTopic)
- Anomaly detection time series
- Engagement heatmaps

---

## 📁 Project Structure

```
cs418-project/
├── data/                                    # Data files and references
│   ├── channel_data.json                   # Channel metadata
│   ├── video_data.json                     # Video metadata
│   └── README.md                           # Data documentation
│
├── plots/                                   # All visualizations
│   ├── Channel Creation by Year.png
│   ├── Video Creation by Time.png
│   ├── View Analysis.png
│   ├── Videos per Channel.png
│   ├── Comments vs Videos.png
│   └── Top Video Categories.png
│
├── task1_data_collection_and_cleanup/      # Data collection scripts
│   ├── channels/
│   │   ├── channel_data_collection.ipynb
│   │   └── channel_data_to_gcp_bq.ipynb
│   ├── videos/
│   │   ├── video_data_collection.ipynb
│   │   └── video_data_to_gcp_bq.ipynb
│   └── comments/
│       ├── comments_data_collection.ipynb
│       └── comment_data_to_gcp_bq.ipynb
│
├── task2_network_analysis/                  # Network science analysis
│
├── task3_engagement_analysis_and_anomaly_detection/
│
├── task4_commenter_level_graph_analysis/    # Commenter networks
│
├── task5_nlp_and_narrative_analysis/        # NLP & topic modeling
│
├── README.md                                # This file
├── LICENSE.md                               # MIT License
└── .gitignore                              # Git ignore rules
```

---

## 🎁 Final Deliverables

### ✅ Completed Deliverables

1. **Final Report** (14 pages)
   - Complete methodology documentation
   - All hypothesis validations with quantitative evidence
   - Individual team member contributions
   - Available in repository root

2. **Network Analysis**
   - Graph visualizations of coordination clusters
   - PageRank top-10 influencer rankings
   - Community detection results (315 communities)
   - Modularity score: 0.9843

3. **Anomaly Detection**
   - 20 statistically significant engagement anomalies identified
   - Visualizations correlating spikes with conflict events
   - Z-score and Isolation Forest analysis results

4. **Engagement Analysis**
   - Power law distribution validation
   - Channel dominance quantification
   - Comment-to-view controversy metrics

5. **NLP & Topic Modeling**
   - BERTopic analysis with 10 coherent topics
   - Narrative evolution timeline plots
   - Multilingual text processing pipeline

6. **All Source Code**
   - Data collection scripts (async API)
   - Cleaning and preprocessing pipelines
   - Analysis notebooks for all tasks
   - Fully documented and reproducible

7. **Visualizations**
   - 5 primary publication-quality figures
   - Interactive network visualizations
   - Topic evolution plots
   - All available in `/plots` directory

---

## 🚀 Installation & Setup

### Prerequisites

- Python 3.8+
- YouTube Data API v3 key
- Google Cloud Platform account (optional, for BigQuery)
- 16GB+ RAM recommended for full analysis

### Required Python Packages

```bash
# Data collection and processing
pip install pandas numpy requests aiohttp
pip install google-cloud-bigquery pandas-gbq

# Network analysis
pip install networkx python-louvain matplotlib seaborn

# Machine learning and statistics
pip install scikit-learn scipy

# NLP and topic modeling
pip install transformers torch sentence-transformers
pip install bertopic umap-learn hdbscan

# Visualization
pip install plotly matplotlib seaborn
```

Or install all at once:

```bash
pip install -r requirements.txt
```

### API Configuration

1. **YouTube Data API v3**:
   - Obtain key from [Google Cloud Console](https://console.cloud.google.com/)
   - Enable YouTube Data API v3
   - Set quota limits (10,000 units/day standard)

2. **Google Cloud BigQuery** (optional):
   - Create project in GCP Console
   - Enable BigQuery API
   - Download service account credentials

3. **Environment Variables**:
   ```bash
   export YOUTUBE_API_KEY="your_api_key_here"
   export GOOGLE_APPLICATION_CREDENTIALS="path/to/credentials.json"
   ```

---

## 💻 Usage

### 1. Data Collection

```bash
# Navigate to data collection directory
cd task1_data_collection_and_cleanup/

# Collect channel data
jupyter notebook channels/channel_data_collection.ipynb

# Collect video data
jupyter notebook videos/video_data_collection.ipynb

# Collect comment data
jupyter notebook comments/comments_data_collection.ipynb
```

**Note**: Data collection can take several hours due to API rate limits.

### 2. Network Analysis

```bash
cd task2_network_analysis/

# Run network construction
jupyter notebook network_construction.ipynb

# Perform community detection
jupyter notebook community_detection.ipynb

# Calculate PageRank centrality
jupyter notebook pagerank_analysis.ipynb
```

### 3. Anomaly Detection

```bash
cd task3_engagement_analysis_and_anomaly_detection/

# Run Isolation Forest
jupyter notebook isolation_forest.ipynb

# Perform Z-score analysis
jupyter notebook z_score_analysis.ipynb
```

### 4. Topic Modeling & NLP

```bash
cd task5_nlp_and_narrative_analysis/

# Run BERTopic analysis
jupyter notebook bertopic_analysis.ipynb

# Track topic evolution
jupyter notebook topic_evolution.ipynb
```

---

## 🔬 Reproducibility

### Reproducing Results

1. **Download Data**:
   ```bash
   # Option 1: Use our cleaned dataset
   # Download from Google Drive link above
   
   # Option 2: Collect fresh data
   # Run data collection scripts in task1/
   ```

2. **Run Analysis Pipeline**:
   ```bash
   # Execute notebooks in order:
   # Task 1 → Task 2 → Task 3 → Task 4 → Task 5
   ```

3. **Generate Visualizations**:
   ```bash
   # All plots regenerated automatically
   # Saved to /plots directory
   ```

### Computational Requirements

- **Data Collection**: ~4-6 hours (API rate limited)
- **Network Analysis**: ~30 minutes (616K nodes)
- **Anomaly Detection**: ~15 minutes (Isolation Forest)
- **Topic Modeling**: ~45 minutes (BERTopic on 20K sample)
- **Total Runtime**: ~6-8 hours end-to-end

### Hardware Specifications

- **Minimum**: 8GB RAM, 4 CPU cores
- **Recommended**: 16GB RAM, 8 CPU cores
- **Storage**: 5GB for data, 10GB for processing
- **GPU**: Optional (speeds up BERT/topic modeling)

---

## 📊 Statistical Summary

### Dataset Characteristics

| Statistic | Value |
|-----------|-------|
| Comments per video (mean) | 2,204 |
| Comments per video (median) | 160.5 |
| Videos per channel (mean) | 2.5 |
| Videos per channel (max) | 1,373 |
| Missing comment text | 756 (0.013%) |
| Temporal range | 20 years |

### Key Performance Metrics

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Network Modularity | 0.9843 | Excellent community structure |
| Gini Coefficient | ~0.85 | Extreme engagement inequality |
| Top 1% View Threshold | 1,000,000+ | Clear viral amplification |
| Controversy Threshold | >0.05 ratio | High-engagement content |
| Anomaly Count | 20 events | Significant conflict correlation |

---

## 🏆 Project Highlights

### Technical Achievements

- ✅ **Scale**: Analyzed 5.9M comments, 440K videos, 1.5K channels
- ✅ **Temporal**: 20-year longitudinal analysis (2005-2025)
- ✅ **Multilingual**: RU/UA/EN content processing pipeline
- ✅ **Multi-method**: 20+ statistical and ML techniques
- ✅ **Validation**: All 3 hypotheses validated with quantitative evidence

### Scientific Contributions

- 📈 **Quantitative thresholds** for coordination detection
- 📊 **Power law distribution** confirms viral amplification
- 🎯 **Temporal correlation** between events and engagement
- 🔍 **Network structure** reveals coordination patterns
- 💬 **Controversy metric** identifies polarizing content

### Academic Quality

- ✅ Rigorous hypothesis-driven approach
- ✅ Multi-method validation (triangulation)
- ✅ Transparent methodology
- ✅ Reproducible results
- ✅ Open source code and data

---

## 📚 References

### Datasets
- FakeNewsNet: Fake news dataset for misinformation research
- LIAR: Large-scale fake news dataset with fact-checking labels
- YouTube Data API v3: Official API for YouTube data collection

### Methods & Libraries
- NetworkX: Graph analysis library
- scikit-learn: Machine learning toolkit
- BERTopic: Neural topic modeling
- python-louvain: Community detection
- sentence-transformers: Multilingual embeddings

### Related Work
- Coordinated information campaigns on social media
- Network analysis of misinformation spread
- Temporal dynamics of online narratives
- Power law distributions in social networks

---

## 📄 License

This project is part of coursework for **CS 418: Introduction to Data Science** at the University of Illinois Chicago (Fall 2025).

**License**: MIT License - See [LICENSE.md](LICENSE.md) for details

**Data Usage**: 
- Collected data complies with YouTube Terms of Service
- API usage follows Google Cloud Platform policies
- No personally identifiable information (PII) collected
- Data available for academic and research purposes

---

## 🙏 Acknowledgments

### Course Staff
- CS 418 instructors and teaching assistants
- University of Illinois Chicago, Department of Computer Science

### Resources
- Google Cloud Platform (API access and BigQuery)
- Google Colab (computational resources)
- Anthropic Claude (documentation assistance)

### Team Collaboration
Special thanks to all team members for their dedicated contributions:
- Data collection and cleaning (Archit)
- Temporal and anomaly analysis (Srinath)
- Engagement and power law analysis (Vishaal)
- Network structure and centrality (Harsh)
- Comment analysis and controversy detection (Vignesh)

---

## 📞 Contact

For questions about this project:

- **Repository Issues**: [GitHub Issues](https://github.com/Archit1706/cs418-project/issues)
- **Team Lead**: Archit Rathod - arath21@uic.edu
- **Course**: CS 418, Fall 2025, UIC

---

## 📅 Project Timeline

- ✅ **Oct 3**: Project proposal submitted
- ✅ **Oct 3-31**: Data collection phase (5.9M comments collected)
- ✅ **Nov 1-14**: Initial analysis and progress report
- ✅ **Nov 15-30**: Advanced analysis and model development
- ✅ **Dec 1-5**: Final visualizations and report writing
- ✅ **Dec 8**: Final submission (COMPLETED)

---

## 🎓 Course Information

**Course**: CS 418 - Introduction to Data Science  
**Semester**: Fall 2025  
**Institution**: University of Illinois Chicago  
**Department**: Computer Science  

**Learning Outcomes Achieved**:
- ✅ Large-scale data collection and processing
- ✅ Exploratory data analysis and visualization
- ✅ Statistical modeling and hypothesis testing
- ✅ Machine learning and anomaly detection
- ✅ Network science and graph analysis
- ✅ Natural language processing
- ✅ Reproducible research practices

---

<div align="center">

### ⭐ If this project helped you, please star the repository! ⭐

**Project Status**: ✅ COMPLETED  
**Submission Date**: December 8, 2025  
**Team**: The Fact Finders  

[📊 View Visualizations](https://github.com/Archit1706/cs418-project/tree/master/plots) | [📄 Read Report](https://github.com/Archit1706/cs418-project/blob/master/report) | [💾 Access Data](https://drive.google.com/drive/folders/1yT8_b9zMD02xL1yyDDLJn0iv2Hus8h5m)

---

**Made with ❤️ by The Fact Finders**  
*Combating misinformation through data science*

</div>
