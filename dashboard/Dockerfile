FROM node:18

WORKDIR /app

RUN git clone https://github.com/typesense/typesense-dashboard.git . \
  && yarn install \
  && yarn build

RUN yarn global add serve

EXPOSE 5000

CMD ["serve", "-s", "build", "-l", "5000"]
