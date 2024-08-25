FROM node:20
EXPOSE 8080
RUN useradd expense
RUN mkdir /opt/app
RUN chown -R expense:expense /opt/app
WORKDIR /opt/app
COPY code /opt/app
RUN npm install
RUN apt install mysql -y
CMD [ "nodes","index.js" ]