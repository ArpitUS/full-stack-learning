# Module 37: Docker Fundamentals

Containerize a runnable Go service so a learner can build and run the same application consistently. Use [Docker Get Started](https://docs.docker.com/get-started/), the [Dockerfile reference](https://docs.docker.com/reference/dockerfile/), and [Docker build best practices](https://docs.docker.com/build/building/best-practices/).

## Learn

- Images versus containers, image layers, registries, tags, container lifecycle, and build context.
- `FROM`, `WORKDIR`, `COPY`, `RUN`, `ENV`, `EXPOSE`, `CMD`, and `ENTRYPOINT`.
- Port publishing versus container networking, bind mounts versus named volumes, and environment configuration.
- Container health checks and the difference between process health, application readiness, and dependency health.

## Practice Deliverable

Containerize one Go HTTP service with a `/health` endpoint. Add a `.dockerignore`, build a tagged local image, publish only the intended port, inject non-secret configuration through environment variables, and demonstrate start/stop/log/inspect workflows.

## Verify

```bash
docker build -t teamops-api:module-37 .
docker image ls teamops-api
docker run --rm -p 8080:8080 --name teamops-api teamops-api:module-37
docker ps
docker logs teamops-api
curl -i http://localhost:8080/health
```

Run the container in a second terminal or omit `--rm` temporarily while learning inspection commands.

## Completion Criteria

- [ ] Explain the image, container, layer, build context, port, and volume roles.
- [ ] Keep source control metadata, dependencies, local environment files, and build output out of the build context where possible.
- [ ] Run the service with explicitly named configuration and port mappings.
- [ ] Inspect logs and container state to diagnose a deliberate startup/configuration failure.
- [ ] Define a health check that proves an application-relevant condition.

## Common Mistakes

Copying the whole repository before dependency files, missing `.dockerignore`, using mutable tags as release identity, publishing ports unintentionally, embedding secrets in an image, assuming `EXPOSE` publishes a port, and interpreting a running process as ready application behavior.

## TeamOps Connection

This module creates the basic API image used in TeamOps Stage 6 and later CI/CD work. Keep the shared production candidate Dockerfile under TeamOps; use this folder for isolated experiments.

## Next

Continue to [Module 38: Docker Advanced](../02-advanced/).
