name: Build

on:
  workflow_run:
    workflows: ["Code Coverage"]

jobs:
  on-success:
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'success' }}
    steps:

      - name: Checkout repository
        uses: actions/checkout@v2
    
      - name: Set up Node.js 20
        uses: actions/setup-node@v1
        with:
          node-version: 20

      - name: Install dependencies
        run: npm install
    
      - name: Success Step
        run: echo 'The triggering workflow passed'

      - name: Build Docker image
        run: |
          docker login -u ${{ secrets.DOCKERHUB_USERNAME }} -p ${{ secrets.DOCKERHUB_TOKEN }}
          docker build -t ${{ secrets.DOCKERHUB_USERNAME }}/ci-js-docker:latest-${{ github.ref_name }}-${{ runner.os }} .
          docker push ${{ secrets.DOCKERHUB_USERNAME }}/ci-js-docker:latest-${{ github.ref_name }}-${{ runner.os }}

  on-failure:
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'failure' }}
    steps:
      - name: Failure Step
        run: echo 'The triggering workflow failed'