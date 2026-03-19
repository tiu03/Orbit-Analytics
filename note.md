# A note for recap and learning about data enginering after that will be some data science and analytic stuff come in

## just keep learning might have something wrong but try first ~_~ for my self hahha  maybe will hide this note someday who know 🦉 i shy

### Phase 1/Week 1: (learning docker and in the mid point try intergrate some CI/CD stull if can)

#### DE  recap + Docker and Spark + Plan for this project

tips: Ctrl+K then V = markdown preview 

Plan using a Hybrid Approach

- (Development): using Local PySpark inside Docker containers. Write and test your code for free without burning Databricks credits or waiting for a cloud cluster to start up.
  - Containerized Ingestion (Docker & PySpark)
- For Production (Scaling): Once script works Run in Databricks note book Spark also
  
docker: 
images - > container 
build images -t <tagname> to run  

Dockerfile:
```docker 

FROM python:3 #from Docker hub 
COPY try.py /try.py #copy from you dir to docker dir
CMD [ "python", "/try.py" ] #run print the python file 

```
try.py:
``` python 
print( "containlization") 
```
terminal :
```bash 
docker build images -t <tagname> #build image 
docker run tagname:latest #ruing the file 
```

#### Docker-Compose.yaml for Multi-container appliaction 
docker-compose.yml


> [!NOTE]
> ``` [docker] 
> docker compose up -d
>```
>The -d flag tells Docker Compose to run containers in detached mode, meaning they start in the background and immediately return control of your terminal while continuing to run.
>
```bash 
docker compose watch #for  keep update the changes from the code and reflex on the app
```
cuz docker isolates all content, code, and data in a container from your local  = when you delete a container within Docker Desktop, all the content within it is deleted.filesystem
when persist data that a container generated use: volumes - 

```docker
todo-database:
    # ...
    volumes:
      - database:/data/db#The volumes element that is nested in todo-database tells Compose to mount the volume named database to /data/db in the container for the todo-database service.
                      
# ...
volumes:
  database:#The top-level volumes element defines and configures a volume named database that can be used by any of the services in the Compose file.
```




---

Medallion Architecture—a data design pattern used to structure data in a lakehouse environment


Data Engineering 
Sources -> Central Hub ->  delivery Insights

Raw data -> Bronze(Raw data ) data untranform data -> Silver (dbt) -> Gold 

[Semantic Layer](https://www.databricks.com/blog/what-is-a-semantic-layer)
[What is Data Architecture?](https://www.databricks.com/blog/what-is-data-architecture)

tips:Data Engineering Roadmap 2026 - Data With Baraa - [my notion private](https://www.notion.so/Data-Engineering-Roadmap-2026-Data-With-Baraa-a7a9cdb8f3ce82dbb046815809f6eb26?source=copy_link)
