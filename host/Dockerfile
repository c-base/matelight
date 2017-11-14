FROM python:3.6
RUN apt-get update && apt-get install -y \
  libusb-1.0-0-dev \
  libbfd-dev \
  python-numpy \
  build-essential
WORKDIR /
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
WORKDIR /host
COPY . .
RUN make
CMD [ "python", "/host/server.py" ]
