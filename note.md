---
title: Note
---

# A note for recap and learning about data enginering after that will be some data science and analytic stuff come in

just keep learning might have something wrong but try first ~_~ for my self   
maybe will hide this note someday who know 🦉 i shy

### **Progress**:
#### Design Data Architecture & Project initialization:

| Epics                    | tasks                       |  - [ ]  |
| ------------------------ | --------------------------- | :-----: |
| Design Data Architecture | Design the Layers           | ongoing |
| Project Initialization   | create git repo & structure |    ✓    |
| Project Initialization   | Commit                      |    ✓    |
Build Bronze Layer: 

| Epics | tasks                     |  ✓  |
| ----- | ------------------------- | :-: |
|       | Analysing: Source Systems |     |
|       | Data Ingestion            |     |
|       | validating                |     |
|       | Document                  |     |
Build Silver Layer: 

| Epics | tasks                                |  ✓  |
| ----- | ------------------------------------ | :-: |
|       | Analysing: Explore & Understand Data |     |
|       | Draw Data Integration                |     |
|       | Coding: Data Cleansing               |     |
|       | Validating: Data Correctness Checks  |     |
|       | Document: Extend Data Flow           |     |
|       |                                      |     |
Build Gold Layer:

| Epics | Tasks                               |  ✓  |
| ----- | ----------------------------------- | :-: |
|       | Analysing: Explore Business Objects |     |
|       | Coding: Data Integration            |     |
|       | Validating: Data Integration Checks |     |
|       |                                     |     |



#### Architecture 
Medallion Architecture: a data design pattern used to structure data in a lakehouse environment

%% Data Engineering 
ETL 
Sources -> Central Hub ->  delivery Insights
Raw data -> Bronze(Raw data ) data untranform data -> Silver (dbt) -> Gold  %%

##### Data layer design 
###### Bronze Layer: 


## Phase a: (learning docker and in the mid point try intergrate some CI/CD stull)

### DE  recap + Docker and Spark + Plan for this [[README|Project]] 



`IDE vscode tips: Ctrl+K then V = markdown preview ` 

#### Plan using a Hybrid Approach
	- (Development): using Local PySpark inside Docker containers. Write and test your code for free without burning Databricks credits or waiting for a cloud cluster to start up.
		- Containerized Ingestion (Docker & PySpark)
	- For Production (Scaling): Once script works Run in Databricks note book Spark also
  
#### Docker: 

images - > container 
build images -t <tagname> to run  

Dockerfile: plain text file 
executes from top to bottom  to build image 
```docker 
FROM python:3 #Pull from Docker hub 
COPY try.py /try.py #copy from you dir to docker dir
CMD [ "python", "/try.py" ] #run print the python file when the container start stored as matadata
```
#### Docker layer instruction order matter 
==Docker only rebuild if change not just use the cached build before make it faster==
FROM 
WORKDIR 
copy decencies 
install npn
copy 


ENV -Available during build AND run etc. api key, db url
EXPORT - Documentation only still need to use -p for publish posts
CMD = when the container start stored as matadata ["entry poin" the Executable  + "," +"CMD" default arguments ] = python app.py the CMD will change  for flexible

**try.py:**
``` python 
print( "containlization") 
```
**terminal :**
```bash 
docker build images -t <tagname> #build image 
docker run tagname:latest #ruing the file 
```
##### Docker-Compose.yaml for Multi-container application 
**docker-compose.yml**
> [!NOTE]
> ``` [docker] 
> docker compose up -d
>```
>The -d flag tells Docker Compose to run containers in detached mode, meaning they start in the background and immediately return control of your terminal while continuing to run.
>
```bash 
docker compose watch #for  keep update the changes from the code and reflex on the app
```
 **volumes:**
 cuz docker isolates all content, code, and data in a container from your local  = when you delete a container within Docker Desktop, all the content within it is deleted.filesystem
when persist data that a container generated use
1.Named volumes
2.[[#Bind Mount]]

```docker
todo-database:
    # ...
    volumes:
      - database:/data/db #The volumes element that is nested in todo-database tells Compose to mount the volume named database to /data/db in the container for the todo-database service.
                      
# ...
volumes:
  database:#The top-level volumes element defines and configures a volume named database that can be used by any of the services in the Compose file.
```
##### Bind Mount
If you want to access data on your system, you can use a bind mount. A bind mount lets you share a directory from your host's filesystem into the container.
```docker
    # ...
    volumes:
      - ./app:/usr/src/app  # mount local folder  ./app  to  /usr/src/app in the container
      - /usr/src/app/node_modules
``` 
This particular bind mount overwrites the static contents of the **/usr/src/app** directory in the container and creates what is known as a development container. The second instruction, **/usr/src/app/node_modules**, prevents the bind mount from overwriting the container's **node_modules** directory to preserve the packages installed in the container.

change the code after bind mount the app keep update after the code updated 
>[!caution]
>obscure


##### Port publishing 
application in the containers each component isolated in own sandbox which mean cant direct access then 
so the port is to break through the isolation and setting  up a forwarding rule etc. host port `8080` forwarded to the container's port  `80` 
Syntax:
	`docker run -d -p HOST_PORT:CONTAINER_PORT nginx` 
	`docker run -d -p 8080:80 nginx`

-  `-p` (or `--publish`) with docker run 
- `HOST_PORT`: The port number on your host machine where you want to receive traffic
- `CONTAINER_PORT`: The port number within the container that's listening for connections

compose.yaml:
```text {collapse=true, title="compose.yaml"}
services:
  app:
    image: docker/welcome-to-docker
    ports:
      - 8080:80
```

> [!IMPORTANT]
>
> When a port is published, it's published to all network interfaces by default. This means any traffic that reaches your machine can access the published application. Be mindful of publishing databases or any sensitive information. ref: Dockerdocs 

##### Docker init:
Containerizing and running a Python application
	Initialize Docker assets
		```
		docker init
		```
then key the details about this project (version and port map blablabal...)

---

#### [[MongoDB]]  

---

#### Python for data engineering (pyspark) 




#### Pyspark
#### Databricks 
#### DBT 













[Semantic Layer](https://www.databricks.com/blog/what-is-a-semantic-layer)
[What is Data Architecture?](https://www.databricks.com/blog/what-is-data-architecture)

tips:Data Engineering Roadmap 2026 - Data With Baraa - [my notion private](https://www.notion.so/Data-Engineering-Roadmap-2026-Data-With-Baraa-a7a9cdb8f3ce82dbb046815809f6eb26?source=copy_link)
 

[^1]: 
