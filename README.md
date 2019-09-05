IRIS
====

An example of a neural network

## About

This project fetches the IRIS dataset from github and trains a sequential neural
network to classify the different flower species in the dataset.

### Install node-red

This project depends on node-red. There is a fork of the project with a working 
docker container [here](https://github.com/jolin1337/nodered-ml)

First thing is to clone this repository and build the docker on the host machine. 
You can decide a port through the envorinment variable.
````
$ git clone https://github.com/jolin1337/nodered-ml
$ cd nodered-ml
$ PORT=1880 docker-compose up
````
Once the docker is built and up and running you should be able to navigate to 
[http://localhost:1880/admin](http://localhost:1880/admin) and setup this repository
in `./projects/IRIRS` to get started.

### Use node-red interface

To be able to experiment with the setup make sure to get familiar with how node 
sends messages between nodes here: 
[https://nodered.org/docs/user-guide/messages](https://nodered.org/docs/user-guide/messages)

## The fun parts

This project consists of 4 flows; Data processing, Model training, Evaluation and Deployment
* The **Data processing** flow makes sure the data is available in the node-red environment
  and prcessing the data accordingly to what the model input needs. To get an overview of the
  dataset you can go to [http://localhost:1880/red-nodes/ui](http://localhost:1880/red-nodes/ui) after 
  this flow has been executed.
* The **Model training** flow you can tweak parameters and execute a training process that 
  will output a model that you can use in evaluation and deployment flows later for 
  evaluation and predictions
* The **Evaluation** flow you are able to do sample predictions and evaluate the model 
  agains an test dataset. After this flow is executed an evaluation website will be 
  available to view the results in different formats at 
  [http://localhost:1880/red-nodes/ui](http://localhost:1880/red-nodes/ui)
* The **deployment** flow is enables you to offer predictions to 3rd party services. The 3rd 
  party services can for example ask node-red service about a flower type.