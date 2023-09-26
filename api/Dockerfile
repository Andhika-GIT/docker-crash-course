# initial layer ( parent image )
FROM node:17-alpine

# define the path in the image directory where we want to put our source code and run our command. In this case, we want to create a folder called app in image directory and put our source code there
WORKDIR /app

# first layer ( copy source code to the image )
COPY . .

# second layer - run the command to install all the dependencies ( this will run on build time, when building the image )
RUN npm install

# define which port is gonna exposed by the container (this is for docker desktop)
EXPOSE 4000

# third layer run the command to run the application ( this command run after the image is ready or after building process is done, and it will run when we start the container )
CMD [ "node", "app.js" ]