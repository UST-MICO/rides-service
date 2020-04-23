
# Rides Service

A Service that generates cloud events containing informations about a completed ride.
Each message contains a randomly generated customer rating between 7 and 10.

## Environment Variables

Variable                              | Implementation Strategy                                                                                                            | default
------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------
LOG_FILE_PATH                         | Path to the file, in which the logs are stored                                                                                     | `<workdir>/test_message_generator.log</workdir>`
LOG_FORMAT                            | The format of the logs. Format variables are described [here](https://docs.python.org/3/library/logging.html#logrecord-attributes) | %(asctime)-15s %(message)s
LOG_LEVEL                             | The log level. Supported values (INFO, DEBUG)                                                                                      | INFO
MESSAGE_SOURCE                        | The value that is used in every message for the CloudEvent field 'source'                                                          | test_message_generator_ + `<random uuid>`
MESSAGE_SEND_INTERVAL                 | The number of seconds between each message                                                                                         | 5
KAFKA_TOPIC_OUTPUT                    | The topic, to which each message is published                                                                                      | test-message-generator
KAFKA_TOPIC_OUTPUT_REPLICATION_FACTOR | The replication factor of the target topic. Only applied, when the message generator has to create the topic manually              | 1
KAFKA_TOPIC_OUTPUT_NUM_PARTITIONS     | The number of partitions of the target topic. Only applied, when the message generator has to create the topic manually            | 1
KAFKA_BOOTSTRAP_SERVERS               | The domain and port of the Kafka broker                                                                                            | localhost:9092
