FROM python:3.6
# Set the locale
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
  libusb-1.0-0-dev \
  libbfd-dev \
  python-numpy \
  build-essential \
  locales
RUN sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    locale-gen
ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8  
WORKDIR /
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
WORKDIR /host
COPY . .
RUN make
EXPOSE 1337/tcp
EXPOSE 1337/udp
CMD [ "python", "/host/server.py" ]
