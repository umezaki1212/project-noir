FROM node:14-alpine

WORKDIR /app

ENV LANG C.UTF-8
ENV TZ Asia/Tokyo

RUN apk update && \
    apk upgrade

EXPOSE 3000

CMD ["yarn", "run", "dev"]
