# Data Pipelines with Airflow
This project will introduce you to the core concepts of Apache Airflow. To complete the project, you will need to create your own custom operators to perform tasks such as staging the data, filling the data warehouse, and running checks on the data as the final step.

We have provided you with a project template that takes care of all the imports and provides four empty operators that need to be implemented into functional pieces of a data pipeline. The template also contains a set of tasks that need to be linked to achieve a coherent and sensible data flow within the pipeline.

You'll be provided with a helpers class that contains all the SQL transformations. Thus, you won't need to write the ETL yourselves, but you'll need to execute it with your custom operators.

![Example Dag](assets/final_project_dag_graph2.png)

## Start the Airflow Web Server
You must have the Docker desktop installed.
```bash
cd cd12380-data-pipelines-with-airflow
docker-compose up -d
```
Once all containers are running, you can view the Airflow web server at http://localhost:8080.

## Set Connections in the Airflow Web Server UI
![Airflow webserver UI. The credentials will be `airflow`/`airflow`.]()
On the Airflow webserver UI page, use `airflow` in both the username and password to login.
* After logging in, add the needed connections through the **Admin > Connections** menu, namely the `aws_credentials` and `redshift` connections.
* Do not forget to start your Redshift cluster from the AWS console.
* After completing all the steps above, you may run your DAG and see if all steps were completed successfully.

## Review the Starter Code
Before you start your development, we recommend you to review the following files:
* `plugins/operators/data_quality.py`
* `plugins/operators/load_fact.py`
* `plugins/operators/load_dimensions.py`
* `plugins/operators/stage_redshift.py`
* `plugins/helpers/sql_queries.py`
* `dags/final_project.py`