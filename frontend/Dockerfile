# Stage 1: Buildin the application
# Install offical Node image
FROM node:24-alpine as build

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build

# Stage 2: Serving the application
FROM node:18-alpine

RUN npm install -g serve

COPY --from=build /app/build ./build

EXPOSE 3000

CMD ["serve", "-s", "build", "-l", "3000"]






