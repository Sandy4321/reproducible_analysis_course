FROM continuumio/miniconda3
MAINTAINER Nikita Kazeev kazeevn@yandex-team.ru

RUN apt-get update
RUN apt-get install -y pkg-config libfreetype6-dev

COPY environment.yml /environment.yml
RUN conda env create -f /environment.yml

RUN /bin/bash -c "source activate open-ml && /bin/bash -c \" \
  pip install git+https://github.com/renatopp/liac-arff.git@03394074deca70db2ff748bbccbbfe284254c54f ; \
  pip install git+https://github.com/openml/openml-python.git@26686b0dda5b08776ef59e8637c5e3cd81dfca00 \
\""

COPY start.sh /root/start.sh
EXPOSE 8888
CMD /root/start.sh
