# stage de build
FROM golang:1.19 AS build

WORKDIR /app

COPY . /app

RUN CGO_ENABLED=0 GOOS=linux go build -o hello hello.go

FROM scratch

WORKDIR /app

COPY --from=build /app/hello ./

EXPOSE 8000

CMD [ "./hello" ]