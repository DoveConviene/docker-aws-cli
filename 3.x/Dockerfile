FROM alpine:latest 
MAINTAINER DoveConviene <server@doveconviene.com> 
RUN apk add --update --no-cache python3 && \
	python3 -m ensurepip && \
    pip3 install --upgrade pip && \
    pip3 install --upgrade --user awsebcli && \
    export PATH=~/.local/bin:$PATH && \
    sed -i 's/self.app_name = self.get_app_name()/self.app_name = self.get_app_name()[0]/' /root/.local/lib/*/site-packages/ebcli/controllers/initialize.py

ENV PATH /root/.local/bin:$PATH
ENTRYPOINT ["eb"]
VOLUME ["/aws"]
WORKDIR /aws
