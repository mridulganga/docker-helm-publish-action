# docker-helm-publish-action
Github Action to publish docker image and helm chart to ECR


## Sample usage
```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v3
      - id: foo
        uses: mridulganga/docker-helm-publish-action@v1
        with:
          who-to-greet: 'Mona the Octocat'
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
```