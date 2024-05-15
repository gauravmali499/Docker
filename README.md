Here is an example of a Dockerfile for a Vite JavaScript project:
Code

FROM node:16-alpine

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "run", "dev"]
This Dockerfile will create an image based on the node:16-alpine image. It will then copy the project's package.json file and install the project's dependencies. Next, it will copy the rest of the project's files into the image. Finally, it will expose port 3000 and start the Vite development server.
To build the image, run the following command:
Code

docker build -t my-vite-app .
To run the image, run the following command:
Code

docker run -p 3000:3000 my-vite-app
This will start the Vite development server on port 3000. You can then access the application at http://localhost:3000.
