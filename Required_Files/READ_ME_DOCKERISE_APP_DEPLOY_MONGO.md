DOCKERIZE APPLICATION - BUILD AND RUN Using Dockerfile


Prerequisites:
GIT Installed
 
Commands to be used: 
1. docker build -t ec2-user/web:v1 .
2. docker run -d -p 3000:3000 ec2-user/web:v1
3. docker ps 
 
DEPLOY MONGODB as DOCKER CONTAINER

1. docker network create mongoCluster
2. docker run -d --rm -p 27017:27017 --name mongo1 --network mongoCluster mongo:5 mongod --replSet myReplicaSet --bind_ip localhost,mongo1
Step 3 and 4 to run If needed to create Secondary and Arbitrary
3. docker run -d --rm -p 27018:27017 --name mongo2 --network mongoCluster mongo:5 mongod --replSet myReplicaSet --bind_ip localhost,mongo2
4. docker run -d --rm -p 27019:27017 --name mongo3 --network mongoCluster mongo:5 mongod --replSet myReplicaSet --bind_ip localhost,mongo3
5. docker ps
6. sudo yum install -y mongodb-mongosh
7. mongosh
8. docker exec -it mongo1 mongosh --eval "rs.initiate({ _id: \"myReplicaSet\", members: [ {_id: 0, host: \"mongo1\"}, {_id: 1, host: \"mongo2\"}, {_id: 2, host: \"mongo3\"}]})"
9. docker exec -it mongo1 mongosh --eval "rs.status()"
10. docker stop mongo1
11. docker exec -it mongo2 mongosh --eval "rs.status()"
