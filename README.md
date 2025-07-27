# k8s_clusters
# 🚀 Projet K8s Cluster avec Flask

Ce dépôt contient les fichiers de configuration et la documentation permettant de construire une application Flask conteneurisée, déployée dans un cluster Kubernetes local via Kind.

## 📦 Objectif

- Créer une application Flask simple
- La conteneuriser avec Docker
- Préparer l’image pour l’utiliser dans un cluster Kind
- Gérer les manifestes Kubernetes (`pod.yaml`, `deployment.yaml`)

## 🧪 Étapes réalisées

1. Création de l’environnement virtuel Python :
   ```bash
   python -m venv venv
   source venv/bin/activate  # ou .\venv\Scripts\activate sur Windows
   pip install flask
   pip freeze > requirements.txt

## ⚙️ Création du cluster Kubernetes avec Kind

Le cluster local est créé via [Kind](https://kind.sigs.k8s.io/) avec la commande :

```bash
kind create cluster --name flask-cluster

```
## 🚀Charger l'image Dokcer dans le cluster Kind

S'assurer que l'image Dokcer local est disponible en local.

```bash
kind load docker-image flask-app:latest --name flask-cluster
```

```md
## 🚀 Déploiement Kubernetes

### 1. 📁 Se placer dans le dossier `manifests/`
```bash
cd manifests
```

### 2. 📦 Appliquer les fichiers YAML
```bash
kubectl apply -f .
```
Cette commande applique tous les fichiers présents dans le dossier `manifests`.

---

## 🔍 Vérification du déploiement

### 1. ✅ Vérifier les Pods
```bash
kubectl get pods
```

### 2. 🧠 Vérifier les Services
```bash
kubectl get svc
```

### 3. 🔎 Voir les logs d’un Pod
```bash
kubectl logs <nom-du-pod>
```

