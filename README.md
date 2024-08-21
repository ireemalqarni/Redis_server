# Redis Deployment on Kubernetes

## Steps to Create the Pod and Service

1. **Create the Redis Pod**
   - Created a `pod.yml` file defining a Redis pod with the latest Redis image.
   - Applied the configuration using:
     ```bash
     kubectl apply -f pod.yml
     ```

2. **Expose the Redis Pod**
   - Created a NodePort service to expose the Redis pod:
     ```bash
     kubectl expose pod redis-pod --port=6379 --name=redis-svc --type=NodePort
     ```

3. **Verify the Deployment**
   - Verified that the Redis pod is running:
     ```bash
     kubectl get pods
     ```
   - Verified the service creation and obtained the NodePort:
     ```bash
     kubectl get services
     kubectl describe service redis-svc
     ```
     The NodePort assigned is `32314`.

4. **Access the Redis Server**
   - Found the Node IP and combined it with the NodePort (`32314`) to access the Redis server.
   - Connected to the Redis server using `redis-cli`:
     ```bash
     redis-cli -h <Node-IP> -p 32314
     ```

## Issues Encountered and Resolutions

- [Document any issues you faced and how you resolved them.]

## Screenshots

- [Attach screenshots for verification of the Redis pod, service details, and Redis client connection.]
