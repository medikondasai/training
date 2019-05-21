# Lab 2.1 - Install AWS SAM and deploy a test function

- Install the AWS SAM CLI.
- Create a function from a template using the CLI.
- Deploy the function using the CLI.
- Update the function to add an API Gateway and event.


## Steps

1. Install the AWS SAM CLI
    - There are multiple ways you can install the CLI depending on what OS you are running and if you prefer to use a brew based package manager.
    - We will use the pip method for linux systems but if you would like to consider another method such as linuxbrew or if you are using a mac use this link for instructions: https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-reference.html

    
        ```bash
        pip install --user aws-sam-cli
        ```
    - Close and re-open your terminal and then run
        ```sh
        sam --version
        ```
        to validate your installation. You should see something similar to:
        ```sh
        SAM CLI, version 0.16.1
        ```
2. Initialize a hello-world function and template
    - Similar to most other frameworks currently (development and otherwise) you can create a simple boiler plate function and template using the CLI to get you started quickly.
    Make sure you are in the folder where you want your code and template file to be created before running this command. It will create a `sam-app` folder wherever it is ran.
    - Initialize a `python 3.7` function and template
        ```sh
        sam init --runtime python3.7
        ```
        you should see something similar to
        ```sh
        2021-01-01 09:49:12 Generating grammar tables from /usr/lib/python3.6/lib2to3/Grammar.txt
        2021-01-01 09:49:12 Generating grammar tables from /usr/lib/python3.6/lib2to3/PatternGrammar.txt
        [+] Initializing project structure...

        Project generated: ./sam-app

        Steps you can take next within the project folder
        ===================================================
        [*] Invoke Function: sam local invoke HelloWorldFunction --event event.json
        [*] Start API Gateway locally: sam local start-api

        Read sam-app/README.md for further instructions

        [*] Project initialization is now complete

        ```
3. Review the files that have been created.
    - In the sam-app folder we have everything we need to deploy a function now. Because this is the hello-world we have now have a `README.md` that is very helpful in explaining all of the parts of SAM and what has been provided to you.
    - You can take a moment to look over that file if you would like, we will cover all of that same information but in a different level of detail with additional information.
    ```bash