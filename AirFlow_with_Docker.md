These tutos were helpful in creating my own

[Running Airflow 2.0 with Docker in 5 mins](https://www.youtube.com/watch?v=aTaytcxy2Ck)

[Airflow DAG](https://www.youtube.com/watch?v=IH1-0hwFZRQ)


# 1 Download and install Docker

[Download and install Docker from here](https://docs.docker.com/get-docker)

Follow the instructions to get it installed 


    *If you are not on windows then you need to seperately install docker-compose.
   [You can Download and install Docker-compose from here](https://docs.docker.com/compose/install/)
   
   Follow the instructions to get it installed

## On windows 
You need to download and install [WLS2 Here](https://docs.microsoft.com/en-gb/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package) and follow the instructions to install. 

Once installed, Next step...

## Create folder and configure for AirFlow installation

From terminal create a directory and download the latest AirFlow .yaml file. 
Commands below

      $  mkdir airflow-docker
      
      $ cd airflow-docker
      
Download the latest AirFlow .yaml file [here](https://airflow.apache.org/docs/apache-airflow/stable/docker-compose.yaml) and copy it into the irflow-docker.

From your terminal within the airflow-docker folder, crete the ./dags ./plugins ./logs folders

Then create and export an environment so you can easily access all the files with the same permission.

      airflow-docker$ mkdir ./dags ./plugins ./logs
      
      airflow-docker$ echo -e "AIRFLOW_UID=$(id -u)\nAIRFLOW_GID=0" > .env
      
      
## Initialize AirFlow instance with the following command

      airflow-docker$ docker-compose up airflow-init
      
      
This is in charge of running the _airflow-init_ service that downloads AirFlow Docker image and its dependencies and creates an AirFlow user with password airflow.

Finally enter the next command to start all the services needed to run AirFlow

      airflow-docker$ docker-compose up
      
      
