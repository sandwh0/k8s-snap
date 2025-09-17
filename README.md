# k8s-snap
This is a training project that shows how to build and run an image processing pipeline on Kubernetes. 

It’s designed to practice and demonstrate modern DevOps skills (Docker, Kubernetes, Helm, ArgoCD, observability, and autoscaling).

# What k8-snap is trying to achieve

A small, production-style pipeline that shows you can design, deploy, and operate a cloud-native system:

1. A user uploads an image to an API.

2. The API writes a job to a queue and records it in a database.

3. A worker picks up the job, processes the image (MVP = mark as “done”; later = resize/convert), and updates the DB.

4. The user checks job status via the API.

# High-level flow 

Client => HTTP /upload => API => Queue => Worker (process job) => Postgres => HTTP /job/{id}
