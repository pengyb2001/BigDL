FROM intelanalytics/bigdl-llm-xpu:2.5.0-SNAPSHOT

ARG http_proxy
ARG https_proxy

# Disable pip's cache behavior
ARG PIP_NO_CACHE_DIR=false

COPY ./entrypoint.sh /opt/entrypoint.sh

# Install Serving Dependencies
RUN cd /llm && \
    pip install --pre --upgrade bigdl-llm[serving] && \
    chmod +x /opt/entrypoint.sh


WORKDIR /llm/
ENTRYPOINT [ "/opt/entrypoint.sh" ]
