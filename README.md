# Dockerfile Bug: Missing requirements.txt and Incorrect CMD
This repository demonstrates a common error encountered when creating Dockerfiles: the missing requirements.txt file, which is referenced in the Dockerfile, and incorrect usage of CMD instruction, leading to build failure. 

## Bug Description
The provided Dockerfile attempts to install dependencies using `pip3 install -r requirements.txt`.  However, the `requirements.txt` file is missing from the context and causes the build to fail. Also, the CMD instruction is incorrectly defined, causing the application to not run as expected. 

## Bug Solution
The solution involves adding a valid `requirements.txt` file and correcting the usage of the `CMD` instruction. This ensures that the dependencies are correctly installed and the application runs within the Docker container.

## How to Reproduce the Bug
1. Clone this repository.
2. Attempt to build the Docker image using `docker build -t my-app .`
3. Observe the build failure due to missing requirements.txt and/or incorrect CMD instruction. 

## How to Fix the Bug
1. Create a `requirements.txt` file with your application's dependencies.
2. Correct the `CMD` instruction in the Dockerfile. 
3. Build the corrected Docker image using `docker build -t my-app .`