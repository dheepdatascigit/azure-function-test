# azure-function-test
Azure function test in python

## Azure fucntion using CLI
- Ref: https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-python?view=iotedge-2020-11&tabs=azure-cli%2Ccmd%2Cbrowser

### System requirements
- Python 3.8 and above
- Azure CLI
- Azure Function Core Tools

### Local environment setup
- Step1: Python Virtual environment
```shell
python -m venv .venv
.venv\scripts\activate
```
You run all subsequent commands in this activated virtual environment.

### Local function project

```shell
func init AzFunctionProject --python
cd AzFunctionProject
```

it will create below files in the dirtory
```shell
<AzFunctionProject>
│   .funcignore
│   .gitignore
│   getting_started.md
│   host.json
│   local.settings.json
│   requirements.txt
│
└───<.vscode>
        extensions.json

```

Add a function to the project using following command, where
  -- name = unique name of the function
  --template = specified the funtion trigger




```shell
func new --name MyHttpExample --template "HTTP trigger" --authlevel "anonymous"

# func new creates a subfolder matching the function name that contains a code file 
<MyHttpExample>
    function.json
    __init__.py

```
- __init__.py contains a main() Python function that's triggered according to the configuration in function.json.

- For an HTTP trigger, the function receives request data in the variable req as defined in function.json. req is an instance of the azure.functions.HttpRequest class. The return object, defined as $return in function.json, is an instance of azure.functions.HttpResponse class. To learn more, see [Azure Functions HTTP triggers and bindings](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-http-webhook?tabs=python).

- function.json is a configuration file that defines the input and output bindings for the function, including the trigger type. We can change scriptFile to invoke a different Python file if desired.
  - Each binding requires a direction, a type, and a unique name. The HTTP trigger has an input binding of type httpTrigger and output binding of type http.

### Run function locally

```shell 
func start
```




