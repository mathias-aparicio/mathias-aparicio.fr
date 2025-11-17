# Can not start redpanda cluster because of deadline

As I was trying to learn how to use redpanda.
I could not create a cluster with `rpk container start`. I got the timeout described in the following code block.

```bash
rpk container start -n 1
Checking for a local image...
Version "redpandadata/redpanda:v25.2.10" not found locally
Pulling image: redpandadata/redpanda:v25.2.10
unable to start cluster: unable to check Redpanda image: could not pull image: context deadline exceeded
```

To solve this issue, first pull the image with

You might want to match the version with the code block above.

```bash
docker pull redpandadata/redpanda:v25.2.10
```

Then retry the container start command.

Hope this help in your learning redpanda journey.
