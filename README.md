### 

#### 

#### What this does:

- Creates 3 nginx replicas
- Sets resource limits (important for learning)
- Exposes via NodePort on port 30080
- Uses alpine image (smaller, faster)

#### Deploy the application
- kubectl apply -f nginx-deployment.yaml​