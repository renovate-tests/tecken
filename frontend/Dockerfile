# Note! If you make changes it in this file, to rebuild it use:
#   docker-compose build frontend
#

# This should match what we have in the Node section of the main Dockerfile.
FROM node:6.12.3@sha256:3b9440aa35903af6f1e64391c4c825223a20bcfb56b51242be6f1db883758cd7

ADD frontend/yarn.lock /yarn.lock
ADD frontend/package.json /package.json
RUN yarn

ENV NODE_PATH=/node_modules
ENV PATH=$PATH:/node_modules/.bin
WORKDIR /app
ADD frontend /app

EXPOSE 3000
EXPOSE 35729


ENTRYPOINT ["/bin/bash", "/app/bin/run_frontend.sh"]
CMD ["start"]
