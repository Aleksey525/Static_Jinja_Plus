FROM ubuntu:24.04

ARG VERSION=0.1.1

RUN apt-get update && \
    apt-get install -y python3 python3-venv git curl && \
    rm -rf /var/lib/apt/lists/*

ENV CHECKSUM_0_1_1=30d9424df1eddb73912b0e2ad5375fa2c876c8e30906bec91952dfb75dcf220b
ENV CHECKSUM_0_1_0=3555bcfd670e134e8360ad934cb5bad1bbe2a7dad24ba7cafa0a3bb8b23c6444

WORKDIR /opt

RUN if [ "$VERSION" = "0.1.1" ]; then \
        CHECKSUM=$CHECKSUM_0_1_1; \
    elif [ "$VERSION" = "0.1.0" ]; then \
        CHECKSUM=$CHECKSUM_0_1_0; \
    else \
        echo "Версия не поддерживается"; \
        exit 1; \
    fi && \
    echo "Контрольная сумма: $CHECKSUM" && \
    curl -L https://github.com/MrDave/StaticJinjaPlus/archive/refs/tags/$VERSION.tar.gz -o /tmp/opt.tar.gz && \
    tar xzf /tmp/opt.tar.gz --strip-components=1 -C /opt && rm /tmp/opt.tar.gz

RUN python3 -m venv venv

RUN ./venv/bin/pip install --no-cache-dir --upgrade pip && \
    ./venv/bin/pip install --no-cache-dir -r requirements.txt

ENTRYPOINT ["./venv/bin/python", "main.py"]
