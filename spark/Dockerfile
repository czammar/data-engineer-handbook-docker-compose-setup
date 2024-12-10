FROM tabulario/spark-iceberg:latest

ENV POSTGRES_JAR_VERSION=42.6.0

RUN curl https://jdbc.postgresql.org/download/postgresql-${POSTGRES_JAR_VERSION}.jar -Lo /opt/spark/jars/${POSTGRES_JAR_VERSION}.jar

# Install Jupyter and other python deps
COPY requirements.txt .
RUN pip3 install -r requirements.txt

# add the spark configuration
COPY spark-defaults.conf /opt/spark/conf