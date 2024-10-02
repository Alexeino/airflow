# Airflow Introduction
It is an open source tool to programmatically author, schedule and monitor workflow.

## Components of Airflow
### WebServer
The webserver provides the UI which allows us to view, manage and monitor your workflow.

### Scheduler
Responsible for determining when your task should run.

### Meta Database
Stores the information about the tasks and their status and other important details. For e.g. Which task has run, their results and status

### Triggerer
It is responsible for managing deferrable tasks for examples tasks that waits for external events to trigger the task.

### Executor
It manages the execution of the task deciding whether to run them in sequence of parallel and on which system.

### Queue
List of tasks waiting to be executed.

### Worker
Processes that actually perform the tasks

## Core Concepts in Airflow

### DAG (Directed Acyclic Graph)
It is a collection of all the task you want to run, organized in a way that reflects their dependencies. It helps you defining the structure of your entire workflow, showing which task needs to happen before others.
It has to be Acyclic meaning this graph shouldn't indicate any loop or cyclic dependenices.

### Operator
An operate is a single, ideally impotent task in your DAG. It's like individual step which produces same output for same input everytime. This allows us to break down workflow into discrete, manageable pieces of work.
Airflow has thousands of Operators such as ...
- PythonOperator for Python script or function
- BashOperator for Bash
- SQLExecuteQueryOperator for SQL query
- FileSensor to wait for a file