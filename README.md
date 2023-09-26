# Testnet Argocd setup

## Setup Argocd 

Instructions from https://argo-cd.readthedocs.io/en/stable/getting_started/
    
    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Open UI and get admin password
    
    kubectl port-forward svc/argocd-server -n argocd 8080:443
    argocd admin initial-password -n argocd

# Deploy

    helm upgrade -n argocd --install localrococo -f localrococo-network.yaml _meta_chart

# Components

- TestnetManager
- Chainspec generator
- Relay Bootnodes
- Relay RPC
- Relay Validators
- Parachains

# TODO

experiment with an appset managing kustomize+helm argo apps