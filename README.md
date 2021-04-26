# GKE Login Action

This action performs login to [GCP] and configuration of `kubectl` for the given [GKE] cluster. It uses 
`gcloud` (Google SDK) command which is [already pre-installed](https://github.com/actions/virtual-environments/blob/main/images/linux/Ubuntu2004-README.md#cli-tools)
on the _ubuntu-latest_ GitHub Runners. 

## Inputs

### `gcp-service-account-key`

**Required** GCP service account key.

### `gke-cluster`

**Required** Cluster ID in GKE.

### `gke-zone`

Zone to use in GKE. Default: `europe-west3-b`.

### `gcp-project-id`

GCP project ID. Default: extracted from `gcp-service-account-key`.

## Outputs

None.

## Example Usage

```yaml
- name: Configure GKE
  uses: 'sendinblue/gke-login-action@v1'
  with:
    gcp-service-account-key: ${{ env.GCP_SERVICE_ACCOUNT_KEY }}
    gke-cluster: ${{ env.GKE_CLUSTER }}
    gke-zone: ${{ env.GKE_ZONE }}
```

[GCP]: https://console.cloud.google.com/ 
[GKE]: https://cloud.google.com/kubernetes-engine
