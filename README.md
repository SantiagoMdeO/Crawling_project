# Crawling_project
i think in this project we are going to be crawling iteso web page, and we are going to be using tools as pyspark and neo4j

# Instructions for myself
### Using dvc

dvc init
dvc add data/dataset.csv
git add 'data\.gitignore' 'data\connections.csv.dvc'
dvc config core.autostage true

git add .
git commit -m "Initial Raw Data"
i and :wq


docker compose up --scale spark-worker=1 -d

docker run -d --restart always 
--publish=7474:7474 --publish=7687:7687 
--env NEO4J_AUTH=neo4j/neo4j@1234 
--volume=data_neo4j:/data 
--name neo4j-iteso 
--network spark_default 
neo4j:2025.09.0