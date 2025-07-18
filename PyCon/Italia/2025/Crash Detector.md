# Crash Detector

https://2025.pycon.it/en/event/crash-detector

Speakers: [Daniele Maccagnola](https://www.linkedin.com/in/danielemaccagnola/), [Angela Addesso](https://www.linkedin.com/in/angela-addesso/)

---

Emergency call: in case of a car accident, sends a message

The black box provides gps position, acceleration data, speed..

Can this data be used to understand if the car was involved in a crash?

Yes, but they receive a lot of signals (200.000 with only 100 accidents). If everything is sent to the operator, then they will be overwhelmed.

A strong filter is needed to remove most false positives.

---

How to decide if an event is at risk?

-> expert knowledge can tell what a crash looks like.

Still, too many false positives.

-> Deep Learning can help

They use a CNN. These are typically used for image classification, they use it to look for the shape of the curves.

Disadvantage: harder to explain the results.
This is a big problem:
- regulatory (AI Act), 
- need to find biases

Their approach:
- shap values (good for biases, less for explanations)
- shapelets: time series subsequences -> capture what shapes are important for the model

kind of metamodel: the feature is whether a subsequence is present in the time series or not

https://www.sktime.net/en/stable/api_reference/auto_generated/sktime.transformations.panel.shapelet_transform.RandomShapeletTransform.html

They introduced a multivariate version

---
 
## Training

BigQuery (stores data, several TBs)

Data processed with DataProc

The model is built with VertexAI, in a training pipeline

## Inference

2 pub sub queues (one for input and one for output) + cloud functions

---

The new version model is always compared with the current model in production. If the new one is not better, then it is not deployed.

Every step of the pipeline is containerized -> this allows to test and execute each test separately (with specific parameters)


