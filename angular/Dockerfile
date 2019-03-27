FROM node:jessie AS builder
EXPOSE 4200
WORKDIR /frontend
COPY . /frontend
RUN npm install
RUN npm install -g @angular/cli
RUN ng build --configuration=production
CMD ["ng","serve","--host=0.0.0.0","--disable-host-check", "--configuration=production"]
