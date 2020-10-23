// create a new directory
mkdir sample-nodejs-app

// change to new directory
cd sample-nodejs-app

// Initialize npm
npm init -y

// install express
npm install express

// create an server.js file
touch a.js

// run the code
node server.js

//Create Dockerfile
docker build -t jobiac_image .

docker run -p 80:3000 {image-id}
docker container ls
docker stop {container-id}

Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:
aws ecr get-login-password --region us-west-2 | docker login --username AWS --password-stdin 811362161349.dkr.ecr.us-west-2.amazonaws.com

Note: If you receive an error using the AWS CLI, make sure that you have the latest version of the AWS CLI and Docker installed.
Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built:
docker build -t jobiak_a .

After the build completes, tag your image so you can push the image to this repository:
docker tag jobiak_a:latest 811362161349.dkr.ecr.us-west-2.amazonaws.com/jobiak_a:latest

Run the following command to push this image to your newly created AWS repository:
docker push 811362161349.dkr.ecr.us-west-2.amazonaws.com/jobiak_a:latest



