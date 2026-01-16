# Deploy SMO via ArgoCD CLI - One Command at a Time

**Run each command, wait for it to complete, check status, then proceed to next.**

---

## Prerequisites

```bash
export KUBECONFIG=~/.kube/config

# Login to ArgoCD (if not already)
ARGOCD_PASSWORD=$(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d)
argocd login localhost:8080 --username admin --password "$ARGOCD_PASSWORD" --insecure
```

---

## Step 1: Deploy/Sync OpenEBS

**If application doesn't exist, create it:**

```bash
argocd app create smo-infra-openebs \
  --repo https://openebs.github.io/openebs \
  --revision 4.3.0 \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace openebs \
  --helm-chart openebs \
  --sync-policy automated \
  --self-heal \
  --auto-prune \
  --project default
```

**If application exists, just sync it:**

```bash
argocd app sync smo-infra-openebs
```

**Check status:**

```bash
argocd app get smo-infra-openebs | grep -E "Sync Status|Health Status"
```

**Wait until you see:**
- Sync Status: `Synced`
- Health Status: `Healthy`

**Then proceed to Step 2.**

---

## Step 2: Deploy/Sync MariaDB Operator

**Create (if doesn't exist):**

```bash
argocd app create smo-infra-mariadb \
  --repo https://helm.mariadb.com/mariadb-operator \
  --revision 25.10.4 \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace mariadb-operator \
  --helm-chart mariadb-operator \
  --sync-policy automated \
  --self-heal \
  --auto-prune \
  --project default
```

**Or sync (if exists):**

```bash
argocd app sync smo-infra-mariadb
```

**Check status:**

```bash
argocd app get smo-infra-mariadb | grep -E "Sync Status|Health Status"
```

**Wait for Synced and Healthy, then proceed.**

---

## Step 3: Deploy/Sync Strimzi

**Create (if doesn't exist):**

```bash
argocd app create smo-infra-strimzi \
  --repo https://strimzi.io/charts/ \
  --revision 0.45.0 \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace strimzi-system \
  --helm-chart strimzi-kafka-operator \
  --sync-policy automated \
  --self-heal \
  --auto-prune \
  --project default
```

**Or sync (if exists):**

```bash
argocd app sync smo-infra-strimzi
```

**Check status:**

```bash
argocd app get smo-infra-strimzi | grep -E "Sync Status|Health Status"
```

**Wait for all 3 infrastructure apps to be Synced and Healthy, then proceed.**

---

## Step 4: Deploy/Sync ONAP

**Create (if doesn't exist):**

```bash
argocd app create smo-onap \
  --repo https://nexus3.o-ran-sc.org/repository/helm.release/ \
  --revision "*" \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace onap \
  --helm-chart onap \
  --helm-set global.postgresql.masterPassword=changeme123 \
  --sync-policy automated \
  --self-heal \
  --auto-prune \
  --project default
```

**Or sync (if exists):**

```bash
argocd app sync smo-onap
```

**Check status (takes 15-30 minutes):**

```bash
argocd app get smo-onap | grep -E "Sync Status|Health Status"
```

**You can proceed to Step 5 while ONAP is deploying.**

---

## Step 5: Deploy/Sync Non-RT-RIC

**Create (if doesn't exist):**

```bash
argocd app create smo-nonrtric \
  --repo https://nexus3.o-ran-sc.org/repository/helm.release/ \
  --revision "*" \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace nonrtric \
  --helm-chart nonrtric \
  --sync-policy automated \
  --self-heal \
  --auto-prune \
  --project default
```

**Or sync (if exists):**

```bash
argocd app sync smo-nonrtric
```

**Check status:**

```bash
argocd app get smo-nonrtric | grep -E "Sync Status|Health Status"
```

---

## Step 6: Deploy/Sync SMO

**Create (if doesn't exist):**

```bash
argocd app create smo-main \
  --repo https://nexus3.o-ran-sc.org/repository/helm.release/ \
  --revision "*" \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace smo \
  --helm-chart smo \
  --sync-policy automated \
  --self-heal \
  --auto-prune \
  --project default
```

**Or sync (if exists):**

```bash
argocd app sync smo-main
```

**Check status:**

```bash
argocd app get smo-main | grep -E "Sync Status|Health Status"
```

---

## Monitor All Applications

**List all:**

```bash
argocd app list
```

**Watch all (updates every 5 seconds):**

```bash
watch -n 5 'argocd app list'
```

**Press Ctrl+C to stop.**

---

## Useful Commands

**Get detailed info about an app:**

```bash
argocd app get <app-name>
```

**Check app logs:**

```bash
argocd app logs <app-name>
```

**Delete an app (if needed):**

```bash
argocd app delete <app-name>
```

**Check pods:**

```bash
kubectl get pods -n openebs
kubectl get pods -n mariadb-operator
kubectl get pods -n strimzi-system
kubectl get pods -n onap
kubectl get pods -n nonrtric
kubectl get pods -n smo
```

---

## Summary

**Order:**
1. OpenEBS → Wait for Healthy
2. MariaDB → Wait for Healthy  
3. Strimzi → Wait for Healthy
4. ONAP → Can proceed while deploying
5. Non-RT-RIC
6. SMO

**Each step:**
1. Run create command (or sync if exists)
2. Check status
3. Wait for Synced/Healthy
4. Proceed to next

---

**End of Guide**

