<div>
	<br/>
	<p>
	    <a href="https://www.npmjs.com/package/@kcp/functions"><img src="https://img.shields.io/npm/v/@kcp/functions.svg?maxAge=3600" alt="NPM version" /></a>
		<a href="https://www.npmjs.com/package/@kcp/functions"><img src="https://img.shields.io/npm/dt/@kcp/functions.svg?maxAge=3600" alt="NPM downloads" /></a>
		<a href="https://packagephobia.now.sh/result?p=@kcp/functions"><img src="https://packagephobia.now.sh/badge?p=@kcp/functions" alt="Install Size"></a>
        <a href="https://dev.azure.com/klasacommunityplugins/Plugins/_build/latest?definitionId=1&branchName=master"><img src="https://dev.azure.com/klasacommunityplugins/Plugins/_apis/build/status/Functions?branchName=master" alt="Build Status"></a>
	</p>
	<p>
    <a href="https://nodei.co/npm/@kcp/functions"><img src="https://nodei.co/npm/@kcp/functions.png?downloads=true&stars=true" alt="NPM info"></a>
  </p>
</div>

# Functions

A simple Klasa plugin which adds reloadable functions to your Klasa Bot

## How To Use

1. Install the plugin.

```bash
npm i @kcp/functions

# If you use yarn
yarn add @kcp/functions
```

1. Use `@kcp/functions` in your client.

```js
const { Client } = require("klasa");
Client.use(require("@kcp/functions"));

new Client({ aliasFunctions: { returnMethod: "run", prefix: "funcs", enabled: true } }).login("Your Beautiful Token");
```

If you use TypeScript

```ts
import { Client } from 'klasa';
import { Client as FunctionsClient } from '@kcp/functions';

Client.use(FunctionsClient);

new Client({ aliasFunctions: { returnMethod: "run", prefix: "funcs", enabled: true } }).login("Your Beautiful Token");
```

1. Create a new `function` in your `functions` folder with the name you want to access later, for example `test.js` or `test.ts`.

```js
const { Function } = require("@kcp/functions");

module.exports = class extends Function {
    run() {
        // Your Code Here
    }
}
```

1. Use these functions in your bot.

```js
this.client.funcs.test();
```

1. ???... Enjoy!

## Tips

- To allow multiple functions in a file so you can do something like `this.client.funcs.utils.toTitleCase(string)` instead of using 1 file per function remove the `returnMethod`.

## License

This project is under the [MIT](https://github.com/KlasaCommunityPlugins/functions/blob/master/LICENSE) license.
