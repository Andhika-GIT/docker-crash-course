# initial layer ( parent image )
FROM node:17-alpine

# first layer - define the workdir
WORKDIR /app

# second layer - copy the package.json to the current workdir
COPY package.json .

# third layer - run the command to install all the dependencies ( this will run on build time, when building the image )
RUN npm install

# fourth layer - copy the entire source code to the current workdir
COPY . .


# fifth layer run the command to run the application ( this command run after the image is ready or after building process is done, and it will run when we start the container )
CMD [ "node", "app.js" ]


# the reason why we copy the package.json first, is that to make the cache of it, so when change our code and creating the image again, the first layer until the third layer will not run again, because there's nothing different about it, only the fourth layer that change, because we change our source code