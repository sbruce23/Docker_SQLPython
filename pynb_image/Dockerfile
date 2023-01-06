FROM python:3.10.9-slim
LABEL maintainer="Scott A. Bruce <sabruce@tamu.edu>"
LABEL version="1.1"
LABEL description="Python Jupyter notebook environment for STAT 624"

RUN apt-get update -y
RUN apt-get install -y gcc
RUN apt-get install -y build-essential libpq-dev
RUN apt-get install -y graphviz

RUN pip install --upgrade pip

RUN pip install numpy==1.23.5  pandas==1.5.2 seaborn==0.12.1 jupyter==1.0.0 scikit-learn==1.1.3 SQLAlchemy==1.4.44 psycopg2==2.9.5 statsmodels==0.13.5 dask[complete]==2022.11.1 graphviz==0.20.1 dask-ml==2022.5.27

WORKDIR /home/notebooks/

EXPOSE 8888

CMD ["jupyter","notebook","--ip=0.0.0.0","--port=8888","--no-browser","--allow-root"]