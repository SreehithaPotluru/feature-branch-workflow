# Feature Branch Workflow: Python CI

This example demonstrates feature-branch development with GitHub Actions.

## Included
- `calculator.py`: sample functions
- `test_calculator.py`: pytest tests
- `requirements.txt`: pytest and Ruff
- `.github/workflows/python-ci.yml`: automatic linting and testing

## Run locally
```bash
python -m pip install -r requirements.txt
ruff check .
python -m pytest -v
```

## Push to GitHub
Create an empty GitHub repository, then run:
```bash
git init
git branch -M main
git add .
git commit -m "Initial project setup"
git checkout -b feature/add-calculator
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin feature/add-calculator
```

Open the repository's Actions tab to see the workflow run. Create a pull request from
`feature/add-calculator` into `main` to trigger the pull-request check.

Note: This workflow reports failures but does not itself block merging. Configure a
branch protection rule or ruleset requiring the `lint-and-test` status check to enforce that.
