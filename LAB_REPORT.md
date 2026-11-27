# AI53 Phase 2 lab report

At each milestone, copy the observed results under **Checkpoint**, then answer the matching **Question** from the Lab Guide.

## Milestone 1 · Inspect the model handoff

### Checkpoint 1 · Evidence

- GitHub repository URL: https://github.com/GouNicolas/AI53_Phase2_Lab_
- Expected model version: phase1-reference-v1
- Three class labels: angular leaf spot, bean rust, healthy
- First pushed commit SHA: 8a1229eecd622fe974a54cf25530d3b2ab2dc52e

### Question 1 · Explanation

Answer:
- GitHub repository URL: https://github.com/GouNicolas/AI53_Phase2_Lab_
- Expected model version: phase1-reference-v1
- Three class labels: angular leaf spot, bean rust, healthy
- First pushed commit SHA: 8a1229eecd622fe974a54cf25530d3b2ab2dc52e

What does the model version identify? What does the Git SHA you just recorded identify?
model version will be used to identify the current model, it will be our champion for the first run.

SHA is just a unique ID for the commit

## Milestone 2 · Serve predictions with FastAPI

### Checkpoint 2 · Evidence

- Final API test count after TODO 1: 7 passed
- Browser prediction JSON for `data/current/leaf-01.jpg`: `{"label":"angular_leaf_spot","confidence":0.5016346573829651,"model_version":"phase1-reference-v1"}`

### Question 2 · Explanation

`/health` only confirms that the service is responding 
`/ready` also confirms that the model loaded and reports its version. Including the model version in each prediction makes it possible to trace which model produced the result and verify it matches the expected release.

## Milestone 3 · Run tests and build in GitHub Actions

### Checkpoint 3 · Evidence

- Local branch: `ci-checks`
- Local commit SHA: `2f0f5c3f91044ac693e3fe9b201a1e44583d80a9`
- Local API test count: 7 passed
- Actions run source (`main`, `PULL REQUEST` or `UNAVAILABLE`): `PULL REQUEST`
- Actions run URL: https://github.com/GouNicolas/AI53_Phase2_Lab_/actions/runs/46008156251
- `tests` job status: `PASS`
- `docker-build` job status: `PASS`
- Container smoke result: `PASS GET /ready (model_version=phase1-reference-v1); PASS GET /health; PASS POST /predict (label=angular_leaf_spot, model_version=phase1-reference-v1)`

For the two job statuses, use `PASS`, `FAIL`, `PENDING`, `SKIPPED`, `CANCELLED` or `UNAVAILABLE`. Use `SKIPPED` when Actions shows that a job was skipped. Use `UNAVAILABLE` for missing CI evidence.

### Question 3 · Explanation

`needs: tests` makes `docker-build` wait for the `tests` job to succeed, so the image is not built and smoke-tested if the API tests fail. After merging, checking the run on `main` verifies CI against the commit actually added to the target branch, rather than only the pull request's trial merge.

## Milestone 4 · Verify a staging release

### Checkpoint 4 · Evidence

- Mode (`RENDER` or `LOCAL`):
- Target URL:
- Tested commit SHA:
- Expected model version from Checkpoint 1:
- Observed model version from `/ready` (`UNAVAILABLE` if it returned none):
- Smoke check result (`PASS` or `FAIL`):
- First error, if any:
- Earlier Render attempt, if switching to local (URL if available and reason for switching):

### Question 4 · Explanation

Answer:

## Milestone 5 · Compare input distributions

### Checkpoint 5 · Evidence

Fill each row from its own `summary.json`. Use the file from the CURRENT report for the first row and the file from the SHIFTED report for the second. In both files, `current_mean` is the mean brightness of the batch you checked. Use the exact `score` (p-value) and `threshold` (cutoff). Enter `DRIFT` when `drift_detected` is true and `NO DRIFT` when it is false.

| Batch | Reference mean (`reference_mean`) | Batch mean (`current_mean`) | Method | Score | Threshold | Result (`DRIFT` or `NO DRIFT`) |
| --- | --- | --- | --- | --- | --- | --- |
| `CURRENT` | | | | | | |
| `SHIFTED` | | | | | | |

- Final full test count:

### Question 5 · Explanation

Answer:
