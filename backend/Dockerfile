FROM node:20
EXPOSE 8080
ENV DB_HOST=mysql
RUN useradd expense
RUN mkdir /opt/backend
RUN chown -R expense:expense /opt/backend
WORKDIR /opt/backend
COPY package.json .
COPY *js .
RUN npm install
CMD [ "node","index.js" ]