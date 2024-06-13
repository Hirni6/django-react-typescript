FROM node:12
WORKDIR /usr/src/app
ARG GTAG_ID
ENV GTAG_ID $GTAG_ID
ARG AUTH_TOKEN
ENV AUTH_TOKEN $AUTH_TOKEN
ENV NODE_ENV production
ADD ./frontend/ /usr/src/app/frontend/
RUN cd frontend \
    && npm ci \
    && echo $'NODE_ENV=production\nAUTH_TOKEN='$AUTH_TOKEN'\nGTAG_ID='$GTAG_ID >> .env \
    && npm run build
