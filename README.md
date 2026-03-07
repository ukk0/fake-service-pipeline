# Fake service repository

This repository demonstrates how a service pipeline can trigger tests from a separate centralized 
test automation repository, using the reusable workflows from GitHub Actions.  

The repository itself contains no real application code or tests, but only the pipeline that 
calls the external test automation workflow from: https://github.com/ukk0/fake-ta-pipeline

## Pipeline flow

```
deploy
  ↓
smoke tests
  ↓
integration tests
  ↓
e2e tests
```

The deployment step is simulated, and once successful each test job will then sequentially call the 
reusable workflow from the test automation repository. A successful test job is always required for the next 
one to be triggered. 
