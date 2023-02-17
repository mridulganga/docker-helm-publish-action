# docker-helm-publish-action
Github Action to publish docker image and helm chart to ECR


## Sample usage
```yaml
on: [push]

jobs:
  docker_helm_publish:
    runs-on: ubuntu-latest
    name: A job to build and publish docker and helm images to ecr 
    steps:
      - uses: actions/checkout@v3
      - uses: mridulganga/docker-helm-publish-action@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: "us-east-1"
          registry: "<aws_account_id>.dkr.ecr.region.amazonaws.com"
          dockerfile: "Dockerfile"
          docker-repo: "service-name"
          docker-tag: "v1.0.0"
          helm-chart: "helm/service-name"
```