Assignment-2:  Dockerfile-Build image with loaded MySQL schema .

        In this assignment we have to write Dockerfile from which we can build our require image to start the container to achive our target. Our target is whenever the container start we should see the database having students table containing your roll number, name and course.
I have used mysql image to build my customize image and to start the container.

Makefile commands :-
  1. make build -> builds image from the Dockerfile
  2. make run   -> create and start container from the built image
  3. make exec  ->  to go inside created container
  4. make clean ->  deletes started container, built image  
  
Getting Started :- 
  
1. Pull the image 

2. make build

3. make run

4. Please make sure that container is running successfully by using docker ps command

5. make exec

6. make clean 

