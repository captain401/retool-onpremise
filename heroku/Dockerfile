FROM tryretool/backend:latest

RUN apt update && apt install openssh-server -y
RUN echo '[ -z "$SSH_CLIENT" ] && source <(curl --fail --retry 3 -sSL "$HEROKU_EXEC_URL")' > /heroku-exec.sh
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

CMD bash /heroku-exec.sh && ./docker_scripts/start_api.sh
