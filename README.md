# Private Repo for tutorial purpose.
This repository will be used to "How to Deploy Private GitHub Repositories to cPanel"

*After this tutorial, this repository will be public.*


*Repository secrets*
- FTP_SERVER
- FTP_USERNAME
- FTP_PASSWORD


*Workflow file name: cPanelDeployment.yml*

```
name: Publish Website to CPanel
on:
  push:
    branches:
      - master
jobs:
  FTP-Deploy-Action:
    name: FTP-Deploy-Action
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2.1.0
      with:
        fetch-depth: 2
    - name: FTP-Deploy-Action
      uses: SamKirkland/FTP-Deploy-Action@3.1.1
      with:
        ftp-server: ${{ secrets.FTP_SERVER }}
        ftp-username: ${{ secrets.FTP_USERNAME }}
        ftp-password: ${{ secrets.FTP_PASSWORD }}
```
