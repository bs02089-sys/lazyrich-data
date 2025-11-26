name: QQQM_IAUM_rebalancing

on:
  workflow_dispatch:   # 수동 실행 가능
  schedule:
    - cron: '30 14 * * *'   # 매일 UTC 14:30 → KST 23:30 실행

jobs:
  update-json:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.12'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run rebalancing script
        run: python QQQM_IAUM_rebalancing.py
        env:
          DATA_REPO_TOKEN: ${{ secrets.DATA_REPO_TOKEN }}
