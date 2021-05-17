# Upload-code-using-FTP-in-github
how to upload code on server using ftp in github?

##Go to your repo.
##Create action in your repo.
##Add below code in your action --




name: CI
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

  workflow_dispatch:

jobs:
   FTP-Deploy-Action:
    name: FTP-Deploy-Action
    runs-on: ubuntu-latest
    steps:
    
    - uses: actions/checkout@v2
      with:
        fetch-depth: 2
    - name: FTP-Deploy-Action
      uses: SamKirkland/FTP-Deploy-Action@3.1.1
      with:
        ftp-server: [Server name]
        ftp-username: [Username]
        ftp-password: [Password]
