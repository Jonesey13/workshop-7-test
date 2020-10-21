FROM alpine:3.9
RUN apk add --update nodejs npm curl bash icu-libs \
krb5-libs libgcc libintl libssl1.1 libstdc++ zlib
RUN adduser -Ds /bin/bash jenkinsuser
USER jenkinsuser
WORKDIR /home/jenkinsuser
RUN curl -sSL https://dot.net/v1/dotnet-install.sh -o dotnet-install.sh
ENV PATH="/home/jenkinsuser/.dotnet:${PATH}"
RUN bash ./dotnet-install.sh