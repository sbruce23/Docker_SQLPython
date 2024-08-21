FROM python:3.10.14-slim
LABEL maintainer="Scott A. Bruce <sabruce@tamu.edu>"
LABEL version="1.3"
LABEL description="Python Jupyter notebook development environment"

RUN apt-get update -y
RUN apt-get install -y gcc
RUN apt-get install -y build-essential libpq-dev
RUN apt-get install -y graphviz

RUN pip install --upgrade pip
 
RUN pip install numpy==2.0.1  
RUN pip install pandas==2.2.2 
RUN pip install seaborn==0.13.2 
RUN pip install jupyter==1.0.0 
RUN pip install scikit-learn==1.5.1 
RUN pip install SQLAlchemy==2.0.32 
RUN pip install psycopg2==2.9.9 
RUN pip install statsmodels==0.14.2 
RUN pip install dask[complete]==2024.8.1 
RUN pip install graphviz==0.20.3 
RUN pip install dask-ml==2024.4.4

WORKDIR /home/notebooks/

CMD jupyter notebook --no-browser --allow-root --ip 0.0.0.0
