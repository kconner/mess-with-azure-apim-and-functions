https://docs.microsoft.com/en-us/azure/api-management/get-started-create-service-instance

```bash
brew install n
n auto
code .
```

https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions

https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-vs-code-typescript

```bash
npm install
```

Run menu > Start Debugging

Accept installation of Azure Functions Core Tools.

- Details: https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=v3%2Cmacos%2Ccsharp%2Cportal%2Cbash%2Ckeda
- If it fails to install, Xcode Command Line Tools may need updating; check the Output log panel. In my case I had a current Xcode version but an old `/Library/Developer/CommandLineTools` that I needed to delete.

```bash
curl 'http://localhost:7071/api/HttpExample'
curl 'http://localhost:7071/api/HttpExample?name=yourself'
```


