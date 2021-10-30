FROM nginx:1.19

COPY ./infra/docker/nginx/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /backend/public

# Nginxの作業ディレクトリを作る
# https://stackoverflow.com/questions/29789268/neterr-incomplete-chunked-encoding-nginx
RUN mkdir /var/lib/nginx && chown nginx:nginx /var/lib/nginx