To publish a message on Apache Pulsar from ABAP, you would need to do the following:

1. Install and configure Apache Pulsar on your system.
2. Import the Apache Pulsar client libraries for ABAP into your ABAP environment.
3. Use the Apache Pulsar client libraries to connect to the Apache Pulsar cluster and create a new client.
4. Use the client to publish a message to a specific topic on the Apache Pulsar cluster.

Here is an example of what this might look like in ABAP code:

```abap
" Import the Apache Pulsar client libraries for ABAP
IMPORT pulsar_client FROM 'pulsar-client-abap'.

" Create a new Apache Pulsar client
DATA pulsar_client TYPE REF TO pulsar_client.
pulsar_client = NEW pulsar_client(
  service_url = 'pulsar://localhost:6650',
  authentication = pulsar_client=>auth_none()
).

" Publish a message to a topic
pulsar_client->producer(topic = 'my-topic')->send(
  message = 'Hello, world!'
).
```

Again, note that this is just an example and may need to be adjusted to match your specific ABAP environment and the configuration of your Apache Pulsar cluster.
