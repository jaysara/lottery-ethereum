# lottery-ethereum
A sample lottery application that uses Ethereum as currency

## Setup Project
* Make sure you have node installed on your laptop. I have used node 9.4 for this project. node 8.0 or greater should work as well.
* Clone the above repository and install the packages with following two commands.
```script
npm install --save solc
npm install --save mocha ganache-cli web3@1.0.0-beta.26
```
#### GitHub Error installing web3
If you get following error where it can not connect to github.
```
1944 silly fetchPackageMetaData Error: Command failed: git clone --template=/Users/jsarl/.npm/_git-remotes/_templates --mirror git://github.com/frozeman/WebSocket-Node.git /Users/jsarl/.npm/_git-remotes/git-github-com-frozeman-WebSocket-Node-git-browserifyCompatible-6c68775e
21944 silly fetchPackageMetaData Cloning into bare repository '/Users/jsarl/.npm/_git-remotes/git-github-com-frozeman-WebSocket-Node-git-browserifyCompatible-6c68775e'...
21944 silly fetchPackageMetaData fatal: unable to connect to github.com:
21944 silly fetchPackageMetaData github.com[0: 192.30.255.112]: errno=Operation timed out
```

Assuming you are not behind any proxy/firewall, you need to specify npm to use https for calling git rather than git:// .

Typing following command fixed this issue.
```script
git config --global url.https://github.com/.insteadOf git://github.com/
```
#### Python Error while installing web3
If you see following kind of error
```
gyp ERR! configure error 
gyp ERR! stack Error: Python executable "/Users/jsarl/anaconda3/bin/python" is v3.6.2, which is not supported by gyp.
gyp ERR! stack You can pass the --python switch to point to Python >= v2.5.0 & < 3.0.0.
npm ERR! scrypt@6.0.3 install: `node-gyp rebuild`
npm ERR! Exit status 1
```
node-gyp fails because of the newer version of python. I am not able to understand, why python is required.
Often, npm packages need to be built first for your OS after downloading. And for performing this, it needs python or a C compiler installed, depending on the package.
It does require older version of python to build

```script
npm config set python /System/Library/Frameworks/Python.framework/Versions/2.7/Resources/Python.app/Contents/MacOS/Python
```
## Run the test
If your project is setup correctly, you can run the tests. If all tests pass, you are good to go.
```script
npm run test
```
