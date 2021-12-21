<!-- start title -->

# GitHub Action:Upload Released Helm Chart to GAR

<!-- end title -->
<!-- start description -->

Extracts a helm chart from a release and uploads it to GAR. This is designed to be run on a release trigger.

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-upload-chart-gar@undefined
  with:
    # Github token to use
    # Default: ${{ github.token }}
    token: ""

    # Release tag to fetch chart from
    # Default: ${{ github.event.release.tag_name }}
    tag: ""

    # gcloud service account credentials json
    credentials-json: ""

    # gcloud project id
    project-id: ""

    # artifact registry region
    # Default: us-central1
    region: ""

    # artifact registry repository
    # Default: charts
    repository: ""

    # the asset name containing the chart, must be a tar file
    # Default: chart.tgz
    release-asset-name: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**                | **Description**                                         |              **Default**               | **Required** |
| :----------------------- | :------------------------------------------------------ | :------------------------------------: | :----------: |
| **`token`**              | Github token to use                                     |         `${{ github.token }}`          |  **false**   |
| **`tag`**                | Release tag to fetch chart from                         | `${{ github.event.release.tag_name }}` |  **false**   |
| **`credentials-json`**   | gcloud service account credentials json                 |                                        |   **true**   |
| **`project-id`**         | gcloud project id                                       |                                        |   **true**   |
| **`region`**             | artifact registry region                                |             `us-central1`              |  **false**   |
| **`repository`**         | artifact registry repository                            |                `charts`                |  **false**   |
| **`release-asset-name`** | the asset name containing the chart, must be a tar file |              `chart.tgz`               |  **false**   |

<!-- end inputs -->
   <!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
   <!-- start examples -->

### Example usage

```yaml
name: Upload Released Chart
on:
  release:
    types:
      - published
jobs:
  upload-chart-gar:
    runs-on: ubuntu-latest
    steps:
      - name: Push Chart
        uses: Unsupervisedcom/action-upload-chart-gar@v1
        with:
          credentials-json: ${{ secrets.GOOGLE_ARTIFACT_READ_WRITE }}
          project-id: ${{ secrets.GOOGLE_ARTIFACT_PROJECT_ID }}
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
