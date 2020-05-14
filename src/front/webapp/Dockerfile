# Set the base image
FROM node:lts-alpine3.9
# Define working directory
WORKDIR /var/www/app

# Install node_modules with yarn
ADD src/front/webapp/src/package.json /tmp/

RUN cd /tmp && yarn --pure-lockfile
RUN mkdir -p /var/www/app && cd /var/www/app && ln -s /tmp/node_modules
# Copy app
COPY src/front/webapp/src /var/www/app
# Expose port
EXPOSE 3000
# Run app
RUN yarn build
# RUN cp -r /var/www/app/dist /var/www/app/src
ENTRYPOINT ["yarn","start"]