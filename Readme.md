this is a normal express application using TS as language
here we will larn about networking (how one docker container talks to another container)
follow following steps

1. Create a network (name can be anything) - run the following command
   cmd = "docker network create <network name>"
2. run a different docker mongo image , giving it a name while attaching it to this network
   cmd = "docker run -d -p 27017:27017 --name <container name> --network <network name> mongo"
3. now run this backend image by replacing the name of the database in connection string int db.ts with the container name of mongo
   cmd = docker run -p 3000:3000 --name <"anything"> --network <network name> <image name>

After following these steps you will see "mongoDB connected" on terminal

good luck!
