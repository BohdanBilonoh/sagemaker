FROM tensorflow/tensorflow:latest-py3

RUN pip install sagemaker-containers scipy scikit-learn

RUN apt-get update && apt-get install -y --no-install-recommends nginx curl
RUN echo "deb [arch=amd64] http://storage.googleapis.com/tensorflow-serving-apt stable tensorflow-model-server tensorflow-model-server-universal" | tee /etc/apt/sources.list.d/tensorflow-serving.list
RUN curl https://storage.googleapis.com/tensorflow-serving-apt/tensorflow-serving.release.pub.gpg | apt-key add -
RUN apt-get update && apt-get install tensorflow-model-server

ENV PATH="/opt/ml/code:${PATH}"

COPY code /opt/ml/code

WORKDIR /opt/ml/code