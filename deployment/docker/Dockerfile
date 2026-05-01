FROM golang:1.24-alpine3.20 AS build

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o /preauthbridge

FROM alpine as runner

WORKDIR /app

COPY --from=build /preauthbridge /preauthbridge

CMD ["/preauthbridge"]