FROM apache/nifi:2.3.0

# Define component versions
ARG NIFI_VERSION=2.3.0
ARG NIFI_LIB_PATH=/opt/nifi/nifi-current/lib
ARG SNOWFLAKE_JDBC_VERSION=3.23.2
ARG ARROW_VERSION=18.2.0
ARG NETTY_VERSION=4.2.0

# Download the Snowflake JDBC driver, Arrow libraries and Snowflake processors
RUN curl -L -o ${NIFI_LIB_PATH}/snowflake-jdbc-${SNOWFLAKE_JDBC_VERSION}.jar https://repo1.maven.org/maven2/net/snowflake/snowflake-jdbc/${SNOWFLAKE_JDBC_VERSION}/snowflake-jdbc-${SNOWFLAKE_JDBC_VERSION}.jar && \
    curl -L -o ${NIFI_LIB_PATH}/arrow-memory-netty-${ARROW_VERSION}.jar https://repo1.maven.org/maven2/org/apache/arrow/arrow-memory-netty/${ARROW_VERSION}/arrow-memory-netty-${ARROW_VERSION}.jar && \
    curl -L -o ${NIFI_LIB_PATH}/arrow-memory-core-${ARROW_VERSION}.jar https://repo1.maven.org/maven2/org/apache/arrow/arrow-memory-core/${ARROW_VERSION}/arrow-memory-core-${ARROW_VERSION}.jar && \
    curl -L -o ${NIFI_LIB_PATH}/arrow-vector-${ARROW_VERSION}.jar https://repo1.maven.org/maven2/org/apache/arrow/arrow-vector/${ARROW_VERSION}/arrow-vector-${ARROW_VERSION}.jar && \
    curl -L -o ${NIFI_LIB_PATH}/arrow-format-${ARROW_VERSION}.jar https://repo1.maven.org/maven2/org/apache/arrow/arrow-format/${ARROW_VERSION}/arrow-format-${ARROW_VERSION}.jar && \
    curl -L -o ${NIFI_LIB_PATH}/netty-buffer-${NETTY_VERSION}.Final.jar https://repo1.maven.org/maven2/io/netty/netty-buffer/${NETTY_VERSION}.Final/netty-buffer-${NETTY_VERSION}.Final.jar && \
    curl -L -o ${NIFI_LIB_PATH}/netty-common-${NETTY_VERSION}.Final.jar https://repo1.maven.org/maven2/io/netty/netty-common/${NETTY_VERSION}.Final/netty-common-${NETTY_VERSION}.Final.jar && \
    curl -L -o ${NIFI_LIB_PATH}/nifi-snowflake-processors-nar-${NIFI_VERSION}.nar https://repo1.maven.org/maven2/org/apache/nifi/nifi-snowflake-processors-nar/${NIFI_VERSION}/nifi-snowflake-processors-nar-${NIFI_VERSION}.nar && \
    curl -L -o ${NIFI_LIB_PATH}/nifi-snowflake-services-api-nar-${NIFI_VERSION}.nar https://repo1.maven.org/maven2/org/apache/nifi/nifi-snowflake-services-api-nar/${NIFI_VERSION}/nifi-snowflake-services-api-nar-${NIFI_VERSION}.nar && \
    curl -L -o ${NIFI_LIB_PATH}/nifi-snowflake-services-nar-${NIFI_VERSION}.nar https://repo1.maven.org/maven2/org/apache/nifi/nifi-snowflake-services-nar/${NIFI_VERSION}/nifi-snowflake-services-nar-${NIFI_VERSION}.nar
