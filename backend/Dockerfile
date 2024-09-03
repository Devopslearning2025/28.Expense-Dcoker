#FROM node:20
#part of resize the image
FROM node:20.15.0-alpine3.20  
EXPOSE 8080
ENV DB_HOST=mysql
#RUN useradd expense
#the above command will not work in alpine image/OS
# RUN addgroup -S expense && adduser -S expense -G expense
# RUN mkdir /opt/backend
# RUN chown -R expense:expense /opt/backend
#for the layer concept
RUN addgroup -S expense && adduser -S expense -G expense \
    $$ mkdir /opt/backend \
    $$ chown -R expense:expense /opt/backend 
WORKDIR /opt/backend
COPY package.json .
COPY *js /opt/backend/
RUN npm install
#to run the backend with expense and not with root 
USER expense
CMD [ "node","index.js" ]