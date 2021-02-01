# GKE Login Action

This action performs login to [GCP] and configuration of `kubectl` for the given [GKE] cluster. It uses 
`gcloud` (Google SDK) command which is [already pre-installed](https://github.com/actions/virtual-environments/blob/main/images/linux/Ubuntu2004-README.md#cli-tools)
on the _ubuntu-latest_ GitHub Runners. 

## Inputs

### `gcp-project-id`

GCP project ID

### `gcp-service-account-key`

GCP service account key.

### `gke-cluster`

Cluster ID in GKE.

### `gke-zone`

Zone to use in GKE. Default: `europe-west3-b`.

## Outputs

None.

## Example Usage

```yaml
- name: Configure GKE
  uses: 'sendinblue/gke-login-action@main'
  with:
    gcp-project-id: ${{ env.GCP_PROJECT_ID }}
    gcp-service-account-key: ${{ env.GCP_SERVICE_ACCOUNT_KEY }}
    gke-cluster: ${{ env.GKE_CLUSTER }}
    gke-zone: ${{ env.GKE_ZONE }}
```

[GCP]: https://console.cloud.google.com/ 
[GKE]: https://cloud.google.com/kubernetes-engine
