To install Minikube on Debian, you can follow these steps:

1. **Update your system:**
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

2. **Install dependencies:**
    ```bash
    sudo apt install -y curl apt-transport-https
    ```

3. **Download and install Minikube:**
    ```bash
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    ```

4. **Verify the installation:**
    ```bash
    minikube version
    ```


## Comandi

**Creare un cluster multinodo**
 ```bash
    minikube start --nodes 2 -p multinode-demo
    NB 
    -p : è il nome che vuoi dare al cluser
    -nodes: è il numero di nodi da fare attenzione perchè il controlplane viene considerato come un nodo quindi se vuoi 1 controlplane e 2 nodi il valore deve essere 3
    ```
**Listare i cluster presenti**
``bash
    minikube profile list   
```

**Cancellare un cluster**
``bash
    minikube delete --profile <nome del cluster>
```
