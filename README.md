# Cocoapods evolution

Repo for datasets and plotting code for On the Usage of Programming Languages in the
iOS Ecosystem, presented in SCAM'22.

## Setup

You will need MongoDB, Python and Jupyter Notebook

Import the datasets into MongoDB:

```bash
cat datasets/cocoapods/* | mongoimport -d ios -c cocoapods
cat datasets/cloc_reports/* | mongoimport -d ios -c cloc_reports
cat datasets/cloc_reports_apps/* | mongoimport -d ios -c cloc_reports_apps
```

Change the parameters of `mongoimport` accordingly to your MongoDB setup. If you don't want to insert the 
ids or they conflict in your database use the `*_no_id.jsonl` versions of the datasets.

Prepare the Python environment:

```bash
virtualenv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook   
```

Load the notebook into Jupyter Notebook, check the configuration to connect to MongoDB and run the notebook.