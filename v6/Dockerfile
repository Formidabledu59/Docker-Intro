FROM alpine:3.20 AS build
RUN apk add --no-cache gcc musl-dev
COPY /app/main.c /src/main.c
RUN gcc /src/main.c -o /src/app

FROM alpine:3.20
COPY --from=build /src/app /usr/local/bin/app
ENTRYPOINT ["app"]
