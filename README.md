# k8s-101
Training land for k8s.

See more detailed study notes in [this google doc](https://docs.google.com/document/d/10sWVrx0WHb7J8dHQrmbF-V2zRghNCSu9OVdpAenBjoE/edit?usp=sharing). Access is restricted.

## Content
- [Basic k8s config file](./pod-def-0.ymlpod-def-0.yml) - the most simple k8s config file to set up a k8s pod.
- [ReplicaSet Config file](./replicaset-def.yml) - skeleton of a ReplicaSet definition file
- [Deployment Config file](./deployment-def.yml) - skeleton of a Deployment definition file
- [Service Definition files](./service/)
- [Namespace Definition file](./namespace.yaml)
- [Resource Quota Definition file](./resource-quota-def.yml)


## Shortcuts

To save time avoid writting up the definition files from scratch, here are som ready to use `kubectrl` commands:

- Create an NGINX Pod

    ```bash
    kubectl run nginx --image=nginx
    ```

- Create a deployment

    ```bash
    kubectl create deployment --image=nginx nginx
    ```

- Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run) and save it to a file.

    ```bash
    kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml
    ```

Then apply the changes with:
    ```bash
    kubectl apply -f nginx-deployment.yaml
    ```
To verify the correctness of a definition file, use this flag:
    ```bash 
    --dry-run=client
    ```