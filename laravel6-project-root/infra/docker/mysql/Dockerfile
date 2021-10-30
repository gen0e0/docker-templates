FROM mysql:8.0

RUN apt-get update \
    && apt-get install --no-install-recommends -y tzdata \
    # Dockerイメージを軽くする
    && apt-get clean \
    && rm -r /var/lib/apt/lists/*

COPY my.cnf /etc/my.cnf
