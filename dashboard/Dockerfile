kFROM node:18

WORKDIR /app

# Download and unzip instead of using git
RUN apt-get update && apt-get install -y unzip curl \
  && curl -L https://github.com/typesense/typesense-dashboard/archive/refs/heads/main.zip -o dashboard.zip \
  && unzip dashboard.zip \
  && mv typesense-dashboard-main/* . \
  && rm -rf dashboard.zip typesense-dashboard-main

RUN yarn install && yarn build

RUN yarn global add serve

EXPOSE 5000

CMD ["serve", "-s", "build", "-l", "5000"]
