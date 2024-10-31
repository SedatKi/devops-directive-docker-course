FROM golang:1.19-alpine as build

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build -o api-golang

###

FROM scratch

COPY --from=build 

CMD ["./api-golang"]