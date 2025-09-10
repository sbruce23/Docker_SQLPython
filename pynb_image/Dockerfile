FROM python:3.13.7-slim
LABEL maintainer="Scott A. Bruce <sabruce@tamu.edu>"
LABEL version="1.4"
LABEL description="Python Jupyter notebook development environment"

RUN apt-get update -y
RUN apt-get install -y gcc
RUN apt-get install -y build-essential libpq-dev
RUN apt-get install -y graphviz

RUN pip install --upgrade pip
 
RUN pip install numpy==2.2.6  
RUN pip install pandas==2.3.2 
RUN pip install seaborn==0.13.2 
RUN pip install jupyter==1.1.1 
RUN pip install scikit-learn==1.7.2 
RUN pip install SQLAlchemy==2.0.43 
RUN pip install psycopg2==2.9.10 
RUN pip install statsmodels==0.14.5 
RUN pip install dask[complete]==2025.9.0 
RUN pip install graphviz==0.21
RUN pip install dask-ml==2025.1.0

WORKDIR /home/notebooks/

CMD jupyter notebook --no-browser --allow-root --ip 0.0.0.0
