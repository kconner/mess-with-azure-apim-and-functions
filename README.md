# Mess with Azure API Manager and Azure Functions

## Use Node LTS

```bash
brew install n
n auto
```

## Set up a free Azure account and an API Manager

Follow: <https://docs.microsoft.com/en-us/azure/api-management/get-started-create-service-instance>

## Create an Azure Function App with an HTTP-triggered function

Open this folder in VS Code.

Install: <https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions>

Follow: <https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-vs-code-typescript>

```bash
npm install
```

Run menu > Start Debugging

Accept installation of Azure Functions Core Tools.

- Details: <https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=v3%2Cmacos%2Ccsharp%2Cportal%2Cbash%2Ckeda>
- If it fails to install, Xcode Command Line Tools may need updating; check the Output log panel. In my case I had a current Xcode version but an old `/Library/Developer/CommandLineTools` that I needed to delete.

While running locally:

```bash
curl 'http://localhost:7071/api/HttpExample'
curl 'http://localhost:7071/api/HttpExample?name=yourself'
```

After deploying:

```bash
az functionapp function show -g <resource group name> -n <function app name> --function-name HttpExample
```

Look for `invokeUrlTemplate`.

```bash
curl '<that>'
curl '<that>?name=yourself'
```

## Import the function app to expose it in APIM

Follow: <https://docs.microsoft.com/en-us/azure/api-management/import-function-app-as-api>

```bash
curl 'https://<APIM subdomain>.azure-api.net/<API path>/HttpExample?name=yourself' -H 'Ocp-Apim-Subscription-Key: <Find this in the Test panel of the APIs list>'
```

## Use APIM from VS Code

Install: <https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-apimanagement&ssr=false#overview>

Read: <https://docs.microsoft.com/en-us/azure/api-management/visual-studio-code-tutorial>
