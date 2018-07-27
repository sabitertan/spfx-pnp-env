# sp-pnp
## DEVELOPMENT ENVIRONMENT FOR SP-PNP
0. NodeJS LTS
    1. Yeoman
    ``` bash
    npm install -g yo gulp
    ```
    2. Yeoman Sharepoint generator
    ``` bash
    npm install -g @microsoft/generator-sharepoint
    ```
1. VSCode

    ### VSCODE PLUGINS

    1. One Dark Pro
    2. EsLint
    3. Babel Javascript
    4. Debugger for Chrome
    5. Beautify
    6. TSLint
    7. vscode-icons
    8. Markdown All in One

2. CMder
### Integrate with VSCode 

- create file 
    `"<< PATH_TO_CMDER >>\vscodeconsole.bat"`
- Add content:
``` bash
@echo off
SET CMDER_ROOT=<< PATH_TO_CMDER >>
"%CMDER_ROOT%\vendor\init.bat"
```

- Open VSCode->File->Preferences->settings
- Edit USER SETTINGS
- add line below 
``` javascript
 "terminal.integrated.shellArgs.windows": 
 ["/K", "<< PATH_TO_CMDER_ESCAPED >>\\vscodeconsole.bat"]
 ```

- to avoid local development environment SSL errors on Chrome:
- Edit : `"<< PATH_TO_CMDER >>\config\user-profile.cmd"`
- Replace content with:
``` bash
:: use this file to run your own startup commands
:: use  in front of the command to prevent printing the command

:: call "%GIT_INSTALL_ROOT%/cmd/start-ssh-agent.cmd"
:: set "PATH=%CMDER_ROOT%\vendor\whatever;%PATH%"
printf "cmder is setting ENV NODE_NO_HTTP2=1\n"
set NODE_NO_HTTP2=1
printf "ENV has been set"
```
