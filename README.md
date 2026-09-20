<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~foke2/3.embed"></iframe>
# Introduction to the project
This repo is the visualization component of a larger capstone project on the Emily Dickinson Archive, built with two collaborators: **Ria De** and **Samantha Chipman**, who worked on other parts of the larger project. This repo — visualizing Dickinson's textual variants — is my own individual contribution. If anyone is interested in working with the Emily Dickinson Archive as data, visit https://www.edickinson.org/

**The full scholarly presentation of this project — with the conceptual framing, contributions to the field, and acknowledgements this README doesn't cover — is published as a Scalar book:** [Dickinsonviz](https://ctsdh.org/dickinsonviz/index/index), hosted by Loyola University Chicago's Center for Textual Studies and Digital Humanities.

**Two things the 2022-23 team started but never finished are now built and published:**
- [`concordance/index.html`](concordance/index.html) — a searchable **Variant Concordance**: 1,400 base-text/variant readings across 412 poems (not just Fascicle 34), turning `data/modified_eda.csv` — an extraction that had sat unpublished since 2022 — into an actual browsable tool, with an honest data-quality note built from cross-checking it against the manuscript-verified Fascicle 34 data below.
- [`PLAN.md`](PLAN.md) and [`results_fascicle34_classification.md`](results_fascicle34_classification.md) — the founding 2022 question ("can Dickinson's variants be traced computationally, even without the skillset at the time?") actually tested: the team's own taxonomy applied, blind, to all 84 manuscript-verified readings in Fascicle 34, pulled directly from the Emily Dickinson Archive's live records at Harvard.



# Extracting Variants in EDA: A Computational Approach
When working with large data, it ususally necessary to specify what foramt/method one needs to use to pull the data from an existing database. 
It's easy to retreive data using API request. In this project, we've utilize the python scraping code to retrieve all files from the webiste since there was no API for the original EDA . See file under code folder for details.


# Data Management Plans for EV
I tried to document in a specific way the data managment plans for this project.
This provides guide in the entire project lifecylce. These include data collection, documentation, storage, sharing, and preservation.
* Data Collection - file formats, naming conventions, version control
    * Script, data, results, docs
* Documentation and Metadata - methodology, code, data dictionaries, metadata standard, README files
* Storage and Backup -  requirements, backup and retention schedules, access controls
    * 3-2-1 rule
* Preservation - see https://zenodo.org/records/10316549
* Sharing and Reuse

# Visualizing Varaints in EDA
The visual representations are saved under data_visualization folder. You can also check the code folder too see and test the code on your own data or on EDA.

# Conclusion
This is data visualization project examining Dickinson's textual variants. There are interesting connections and relationship that base texts share with their corresponding variants. 


![newplot(7)](https://github.com/bfiliks/extractVariants/assets/37164388/940199dc-5f7a-47be-b020-477b5eebf2c9)
