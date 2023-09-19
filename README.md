## Spark Docker Scalable

**Description:**

This repository provides a scalable Apache Spark cluster setup using Docker Compose. It allows you to easily scale the number of Spark workers based on your requirements.

**Usage:**

To launch the Spark cluster with a specific number of workers, use the following command:

```shell
docker-compose up --scale spark-worker=<number_of_workers>
```

### Accessing Web Interfaces:
Spark History Server:
    Access the Spark History Server UI at http://localhost:18080 to monitor the history of completed Spark applications.

Spark UI:
    During the runtime of a submitted Spark job, you can access the Spark UI at http://localhost:4040 to monitor the progress and details of the Spark application.

Example Spark Job:
The docker-compose.yml file includes a spark-app container that runs an example Spark job. You can replace this with your own Spark application or modify it to meet your needs.
