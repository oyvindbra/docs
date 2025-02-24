---
title: Probes
weight: 1
---
Probes should not require authorization.

Any code greater than or equal to 200 and less than 400 indicates success. Any other code indicates failure.

## Readiness
A readiness probe is used to check whether the service is ready to accept connections.

In the deployment.yaml, you define the readiness probe. Example:
```
readinessProbe:
   httpGet:
      path: /ready
      port: 8080
   initialDelaySeconds: 20
   periodSeconds: 30
   successThreshold: 1
   failureThreshold: 5
```
We should check if the runtime dependencies that the service absolutely need to function, is ready. If the service depends on a database, it should check if the database is ready.

## Liveness
A liveness probe is used to check whether the service has gone into a broken state.

In the deployment.yaml, you define the readiness probe. Example:
```
livenessProbe:
   httpGet:
      path: /ping
      port: 8080
   initialDelaySeconds: 20
   periodSeconds: 30
   successThreshold: 1
   failureThreshold: 5
```
An implementation (in java/kotlin) would be simply
```
@RequestMapping(value = ["/ping"], method = [GET])

fun ping(): ResponseEntity<Void> =
        ResponseEntity.ok().build()
```

# References
The following is a nice intro for Spring Boot: https://www.baeldung.com/spring-boot-kubernetes-self-healing-apps
Kubernetes configuration: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-probes/
Example with authorization: https://www.critiqus.com/post/kubernetes-health/
