<!-- start title -->

# GitHub Action:Hello World

<!-- end title -->
<!-- start description -->

Greet someone

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-composite-action-template@undefined
  with:
    # Who to greet
    # Default: World
    who-to-greet: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**          | **Description** | **Default** | **Required** |
| :----------------- | :-------------- | :---------: | :----------: |
| **`who-to-greet`** | Who to greet    |   `World`   |   **true**   |

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
