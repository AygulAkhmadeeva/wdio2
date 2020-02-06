# Setup # 

## Create New Project through terminal ##
Open the directory in terminal where you want to create your new project. Initialize a new NPM project. To do this, run the following commands in terminal:

mkdir wdio-test (create directory) cd wdio-test (open just created directory) npm init -y (initialize)

## Install WebdriverIO CLI ##

```npm i --save-dev @wdio/cli```

## Generate Configuration File ##

```./node_modules/.bin/wdio config -y```

## Create Special files ##
We create test file. We going to store all of your test files in a new folder.
Create the test folder like this:

```mkdir -p ./test/specs```
Create a new file in that folder:

```touch ./test/specs/register.js```

## Open that file, and write the following code in it ##

const assert = require('assert')

describe('webdriver.io page', () => {
    it('should have the right title', () => {
        browser.url('https://webdriver.io')
        const title = browser.getTitle()
        assert.strictEqual(title, 'WebdriverIO · Next-gen WebDriver test framework for Node.js')
    })
})

## 2.4 Install Chai ##
Run the below commands in terminal or cmd:

```npm install chai```

Write the following command at the top of register.js file to be able to use Chai syntax:

```const {expect} = require('chai');```

Now we can create our tests using Chai syntax: expect.equal form;

## Run tests ##
To run test run the following command in terminal:

```./node_modules/.bin/wdio wdio.conf.js```

To run tests automatically from 'npm test' command in terminal, add the above comment in package.json file after test, so it will look like this: "test": "./node_modules/.bin/wdio wdio.conf.js"
