# harperdb-observability
Harperdb Interview Coding  Challenge 

# PROJECT INTENT
This project is about deploying a lightweight, containerized instance of HarperDB using Docker.My goal is to make it easy to spin up, monitor, test and collect some performance metrics.

I built this using GitHub Actions for CICD, so everything I push a code, it automatically spins up the HarperDB container, runs a test, capture metrics, adn print a small report.

# HOW to Execute the Workflow

After cloning this repo and pushing the changes to main branch:

1. GitHub Actions will automatically trigger the workflow in (.github/workflows/main.yml)

2. The triggered workflow
  2a. Spins up HarperDB using docker compose
  2b. pings the API to make sure its running
  2c. inserts test data
  2d. updates the datat
  2e. reads to verify
  2f. captures the container stats a outputs it to a file (metrix.txt)
  2g. runs a tiny python script (report.py) to show the metrics

  # Commands to run locally

  docker compose up -d (to run in the background)
  python report.py (to genereate the report)

  # View the Report
  I made the report part of the workflow so there is less to do manually. You can view it by:

  1. Once in the GitHub repo, on the top left click on the Actions tab.
  2. There will be two workflow runs displayed click on the one titled "HarperDB container Test #2" or "created a scripte that generate a report"
  3. Next click on the "test-harperdb"
  4. Scroll down the jobs until you see "Generate metrics report"

  Here you will see a table from the metrics.txt that shows the container ID, Name, CPU, MEM usage/limit, MEM %, NET I/o and Block I/O

  Thank you!
  Nellie Umanah 😊

