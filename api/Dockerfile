# initial layer ( parent image )
FROM node:17-alpine

# first layer - install nodemon, to watch any changes in code
RUN npm install -g nodemon

# second layer - define the workdir
WORKDIR /app

# third layer - copy the package.json to the current workdir
COPY package.json .

# fourth layer - run the command to install all the dependencies ( this will run on build time, when building the image )
RUN npm install

# fifth layer - copy the entire source code to the current workdir
COPY . .

EXPOSE 4000

# sixth layer run the command to run the application ( this command run after the image is ready and we want to start the container )
CMD [ "npm", "run", "dev" ]


# the reason why we copy the package.json first, is that to make the cache of it, so when change our code and creating the image again, the first layer until the third layer will not run again, because there's nothing different about it, only the fourth layer that change, because we change our source code