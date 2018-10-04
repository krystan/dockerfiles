FROM alpine:latest
LABEL maintainer "Krystan Honour <krystan@gmail.com>"

ADD https://github.com/gruntwork-io/terragrunt/releases/download/v0.16.14/terragrunt_linux_amd64 terragrunt

RUN chmod +x terragrunt

FROM hashicorp/terraform:latest
COPY --from=0 terragrunt /usr/local/bin/

ENV TERRAGRUNT_IAM_ROLE ""
ENV AWS_ACCESS_KEY_ID ""
ENV AWS_SECRET_ACCESS_KEY ""

ENTRYPOINT ["/usr/local/bin/terragrunt"]
