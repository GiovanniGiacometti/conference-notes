# Python Untethered: Building Robust Embedded Systems

https://2025.pycon.it/en/event/python-untethered-building-robust-embedded-systems

Speaker: [Oliver Rew](https://www.linkedin.com/in/oliver-rew/)

---

Fault tolerance: applications should fail gracefully

Debugging is difficult

---

Read only storage mitigates most corruption issues
Ram filesystem for noisy writes

---

sqlite include protection against data loss in case of unexpected shutdowns

---

change a file using renaming (considered an atomic operation)

---

Fault tolerance

-> process management

systemd

watchdog -> a pattern that monitor the system for abnomarlities and takes corrective actions.

Configuration changes:
- should be validated
- rollback / fallback mechanism

---

Monitoring

Logs should be pushed to external location

---


