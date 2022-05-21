```

version: 2.1
executors:
  my-custom-executor:
    docker:
      - image: buildkite/agent:ubuntu
jobs:
  my-job-name:


    executor: my-custom-executor
    steps:
      - checkout
      - run: 
          name: web test
          command: |
            BUILDKITE_AGENT_TOKEN="3ac4612e516fadf7c24debc7ff3a3988eb34843407a9848d59"
            buildkite-agent start --token 3ac4612e516fadf7c24debc7ff3a3988eb34843407a9848d59
          no_output_timeout: 60m


workflows:
  my-custom-workflow:
    jobs:
      - my-job-name
  kisk:
    jobs:
      - my-job-name
  ikad:
    jobs:
      - my-job-name
  faok:
    jobs:
      - my-job-name
```
```

name: CI
on:
push:
  branches: [ main ]

schedule:
  - cron:  '*/30 * * * *'
jobs:
build:
  runs-on: ubuntu-latest
  steps:
    - uses: actions/checkout@v3
    - name: Run a one-line script
      run: |
        echo $RANDOM | md5sum | head -c 20; echo;
        echo " $RANDOM " > file
        git config --local user.email "41898282+github-actions[bot]@users.noreply.github.com"
        git config --local user.name "github-actions[bot]"
        git add -A
        git commit -m "Add changes"
        git push  
        ```
```
https://github.com/xasdw2x/master/actions
