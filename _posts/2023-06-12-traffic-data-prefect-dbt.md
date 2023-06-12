---
title: Transforming Chicago traffic crash data with Prefect and dbt
---

I put together a [data engineering and analysis project](https://github.com/datatoolsrc2023/chicago_traffic_crashes) using data I had already started exploring from the [Chicago Data Portal](https://data.cityofchicago.org/) (specifically, [traffic crashes data](https://data.cityofchicago.org/browse?q=Traffic%20Crashes%20-%20Crashes&sortBy=relevance)). (Originally I was interested in exploring and analyzing this data to see if there was any correlation between accident severity and particular make/model/year of car, specifically newer makes and models with higher profiles and decreased visibility.)

I structured the first version of this project as a series of tasks, with each task in a separate directory that held a handful of Python scripts (setup, test, etc) and a Makefile to coordinate their execution. To execute all tasks, I switched into each directory and ran `make`; I intended to write a higher-level script to automate that bit later. However, I decided to refactor the project with [Prefect Core](https://docs.prefect.io/2.10.13/) and [dbt Core](https://docs.getdbt.com/) to get more experience with industry-standard tools.

## Prefect

I've enjoyed using Prefect for orchestration -- it's got a lot of nice features without being too configuration-heavy (looking at you, Dagster). It was easy to start small with one Python file for tasks and flows, and add functionality as I needed it (a common.py file for commonly-used functions, deployment.py to define a deployment schedule.) I've mostly been running Prefect on the command line, but it's been nice to fire up the server and see all my runs and scheduled deployments.

I defined the following tasks and flows in Prefect:
- Download CSVs of crashes, vehicles, and people data from the Chicago Open Data Portal website. (There's a JSON API, but for the purposes of this project, I found it faster and easier to just download the CSVs.)
- Load data from the CSVs into raw tables.
- Kick off a run of dbt to build models of staging tables and analytics views built on the staging tables.

## dbt

I originally intended this project to be an exercise in making an (almost) entirely SQL-based ETL pipeline to sharpen my SQL skills, so dbt felt like a natural fit when it came time to refactor. Things I've liked about dbt:
- It is very easy to define models and their relationships to each other and see how those models change over time.
- Testing is a breeze, and actually kind of fun.

Things that have been a little funky:
- if you create a YAML config file in the `/models` directory, it overrides the main YAML config file in the project's top-level directory. Which makes sense *except* for the fact that having a `/models` config seems to blow away unrelated settings defined in the top-level directory config. For example: in my top-level config, I'd set the default materialization for `/models/base_tables` to `table`, but the mere presence of a model-level config file with an unrelated setting (in my case, a source) caused those models to be materialized as views. I'm guessing this is because the presence of the model-level config imports a bunch of default settings at the model level, which then override the project-level settings. Not the biggest deal, since I just set the materialization at the top of those model files, but it was still confusing to debug. (I also assume I can set the materialization for those models in the `/models` config file, but I'm having trouble getting the syntax right.)

## Future work

Lots of stuff!

- Use the JSON API instead of downloading CSVs
- Add more tests, for both Prefect tasks/flows and dbt models
- Add more analytics models to dbt
