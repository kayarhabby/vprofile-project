# fetch the default image of nginx
FROM nginx
# label
LABEL "Project"="Vprofile"
LABEL "Author"="Rhabby"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf