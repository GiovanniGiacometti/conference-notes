https://2025.pycon.it/en/event/boosting-python-web-apps-performance-with-celery-and-concurrency

Speaker: Yash Raj

Web frameworks:

- handle requests

not meant for:

- scraping
- running a ml model
- sending emails


What to do?

**Celery**: fifo approach to handle tasks

It is used with rabbitmq and redis

---

Concurrency

8 cores

each core can handle 2 threads -> 16 threads

with celery:

- process: 1 process per core
- threads: resources are shared

the worker fetches the task from the queue and execute them in each thread

---

cli commands

--pool -> prefork / threads
--concurrency -> the size of the pool
--autoscale -> automatically scale the number of workers