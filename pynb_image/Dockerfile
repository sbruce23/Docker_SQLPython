FROM python:3.12.1-slim
LABEL maintainer="Scott A. Bruce <sabruce@tamu.edu>"
LABEL version="1.2"
LABEL description="Python Jupyter notebook development environment"

RUN apt-get update -y
RUN apt-get install -y gcc
RUN apt-get install -y build-essential libpq-dev
RUN apt-get install -y graphviz

RUN pip install --upgrade pip

RUN pip install numpy==1.26.3  pandas==2.2.0 seaborn==0.13.2 jupyter==1.0.0 scikit-learn==1.4.0 SQLAlchemy==2.0.25 psycopg2==2.9.9 statsmodels==0.14.1 dask[complete]==2024.1.1 graphviz==0.20.1 dask-ml==2023.3.24

WORKDIR /home/notebooks/

CMD ["jupyter","notebook","--ip=0.0.0.0","--port=8888","--no-browser"]
