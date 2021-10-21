FROM python:3.10

RUN pip install awscli ecs-deploy --upgrade

RUN groupadd --gid 999 docker
RUN groupadd --gid 1000 jenkins
RUN adduser --gid 999,1000 --uid 1000 --disabled-password --gecos '' jenkins

USER jenkins
