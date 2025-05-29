# The essense of Graceful Shutdown

https://2025.pycon.it/en/event/the-essense-of-graceful-shutdown

Speaker: [Andrii Soldatenko](https://www.linkedin.com/in/andriisoldatenko/)

---

Graceful shutdown -> process where programs are terminated in a controlled manner (release resources, close files)

1. Sync

We can simply try-except but the job we are currently running will be interrupted

Or the exception can happen outside the try except

**Signal handler**

signal library that can be used as a callback 

This is robust to different error signals.

signals are signals that the operating system sends to the process

There is no standard (nginx, docker, kubernetes) on the signal sent to shutdown the process


kubernetes sends SIGTERM and then after a timeout it sends SIGKILL
In this way you have time to handle the shutdown

30 seconds is default but it would be better to set it to less time.

K8S deletes pods all the times, it always does this reconciling job.

2. Async

Still we use signal handler

- find all running tasks
- cancel each task

---

You can't register a signal handler for sigkill

We clean up on sigterm

there is no way to handle sigkill using kubectl

---

Stopsignal -> docker file command

You can use it to change the signal that kills the process

You can define on pod level the stop signal

---

Many options for deployments

Rainbow deployment (like green\blue but with more than 2 versions)

---