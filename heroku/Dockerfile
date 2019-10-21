FROM tryretool/backend:latest

RUN mkdir -p /app/.profile.d
RUN echo '[200~[ -z "$SSH_CLIENT" ] && source <(curl --fail --retry 3 -sSL "$HEROKU_EXEC_URL")' > /app/.profile.d/heroku-exec.sh
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

CMD bash heroku-exec.sh && ./docker_scripts/start_api.sh
