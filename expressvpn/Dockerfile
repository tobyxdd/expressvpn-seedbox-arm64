FROM debian:bullseye-slim

ENV ACTIVATION_CODE Code
ENV LOCATION smart
ENV PREFERRED_PROTOCOL auto
ENV LIGHTWAY_CIPHER auto

ARG APP=expressvpn_3.24.0.2-1_armhf.deb

RUN dpkg --add-architecture armhf \
    && apt-get update && apt-get install -y --no-install-recommends \
    libc6:armhf libstdc++6:armhf \
    libterm-readkey-perl ca-certificates wget expect iproute2 curl procps libnm0 \
    && rm -rf /var/lib/apt/lists/* \
    && ln -s /lib/arm-linux-gnueabihf/ld-2.23.so /lib/ld-linux.so.3 \
    && wget -q "https://www.expressvpn.works/clients/linux/${APP}" -O /tmp/${APP} \
    && dpkg -i /tmp/${APP} \
    && rm -rf /tmp/*.deb \
    && apt-get purge -y --auto-remove wget

COPY entrypoint.sh /tmp/entrypoint.sh
COPY expressvpnActivate.sh /tmp/expressvpnActivate.sh

ENTRYPOINT ["/bin/bash", "/tmp/entrypoint.sh"]
