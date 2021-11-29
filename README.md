# Delete kafka records from a topic without deleting the topic

For a topic with 8 partitions:

Create a file `kafka-topic-partitions.json`:

```json
{
    "partitions": [
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 0,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 1,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 2,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 3,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 4,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 5,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 6,
            "offset": -1
        },
        {
            "topic": "pre-pipeline-wse-feature-ork-9-sends-command-pp-long-task",
            "partition": 7,
            "offset": -1
        }
    ],
    "version": 1
}
```

Then run the following: 

```bash
kafka-delete-records --bootstrap-server dev-eu-k8s-01-light-brokers-0:9092 --offset-json-file kafka-topic-partitions.json

Executing records delete operation
Records delete operation completed:
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-7	low_watermark: 11
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-5	low_watermark: 9
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-6	low_watermark: 8
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-0	low_watermark: 9
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-3	low_watermark: 8
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-4	low_watermark: 9
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-1	low_watermark: 10
partition: pre-pipeline-wse-feature-ork-32-pipeline-callback-2	low_watermark: 8
```