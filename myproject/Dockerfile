FROM alpine:3.12
COPY lcs /usr/src/lcs
COPY myproject/*.py /usr/src/myproject/
COPY myproject/requirements.txt /usr/src/myproject
COPY myproject/static /usr/src/myproject/static
COPY myproject/templates /usr/src/myproject/templates
RUN apk add --no-cache python3 py3-pip bash \
    && pip install /usr/src/lcs \
    && pip install -r /usr/src/myproject/requirements.txt
RUN pip install markupsafe==2.0.1
WORKDIR /usr/src/myproject
ENTRYPOINT python3 main.py
