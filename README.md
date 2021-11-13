# Piper workflow engine exploration
This is a sample project to explore the capabilities and limitations of the piper workflow engine.

Instructions to run:
* Edit / add pipelines (.yaml) under piplelines folder.
* Start the docker containers
  ```
  docker-compose up -d
    ``` 


* Create a workflow/job instance
    ```
    curl -s \
         -X POST \
         -H Content-Type:application/json \
         -d '{"pipelineId":"flows","inputs":{"name":"shashank"}}' \
         http://localhost:8080/jobs
    
    ```

* Monitor logs for the job execution output: 
  - Sample logs:
    ```
    piper_1     | Hello shashank. Lets explore various flows!!!
    piper_1     | branch1-task1
    piper_1     | branch2-task1
    piper_1     | branch1-task1-parallel1
    piper_1     | branch1-task1-parallel2
    piper_1     | branch2-task1-parallel1
    piper_1     | branch2-task1-parallel2
    piper_1     | branch1-task2
    piper_1     | branch2-task2
    piper_1     | fork2-branch1-task1
    piper_1     | fork2-branch2-task1
    piper_1     | fork2-branch1-task2
    piper_1     | fork2-branch2-task2
    piper_1     | branch2-task3
    piper_1     | nested-parallel1-task1
    piper_1     | nested-parallel1-task2
    piper_1     | nested parallel2
    piper_1     | Goodbye shashank! Hope that is enough understanding for now!!!
    ```
