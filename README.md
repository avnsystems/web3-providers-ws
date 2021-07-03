<p align="center">
  <a href="#">
    <img src="https://raw.githubusercontent.com/allanavelar/website/gh-pages/static/images/icons/icon-256x256.png" height="256">
    <h1 align="center">Web3 Providers WebSocket</h1>
  </a>
</p>

<p align="center">
  <a href="#">
    <img src="https://img.shields.io/npm/v/web3-providers-ws.svg?style=for-the-badge" alt="language-used"/>
  </a>

  <a href="#">
    <img src="https://img.shields.io/github/languages/top/avnsystems/web3-providers-ws.svg?style=for-the-badge" alt="language-used"/>
  </a>

  <a href="#">
    <img src="https://img.shields.io/github/contributors/avnsystems/web3-providers-ws.svg?style=for-the-badge">
  </a>

  <a href="#">
    <img src="https://img.shields.io/github/forks/avnsystems/web3-providers-ws.svg?style=for-the-badge">
  </a>

  <a href="#">
    <img src="https://img.shields.io/github/stars/avnsystems/web3-providers-ws.svg?style=for-the-badge">
  </a>

  <a href="#">
    <img src="https://img.shields.io/github/issues/avnsystems/web3-providers-ws.svg?style=for-the-badge">
  </a>

  <h3 align="center">This is a fork of web3-providers-ws that uses <a href="https://github.com/avnsystems/websocket-node">@avnsystems/websocket-node</a></h3>
</p>

## Overview

This is a websocket provider sub-package for [web3.js][repo].

Please read the [documentation][docs] for more.

## Installation

### Node.js

```bash
npm install @avnsystems/web3-providers-ws
```

## Usage

```js
const AVNWeb3ProvidersWs = require('@avnsystems/web3-providers-ws');

const options = {
    // Enable keepalive 
    clientConfig: {
        keepalive: true,
        keepaliveInterval: 60000,
        keepaliveForce: true
    },
    // Enable auto reconnection
    reconnect: {
        auto: true,
        delay: 5000, // ms
        maxAttempts: 5,
        onTimeout: false
    }
};

const wsProvider = new AVNWeb3ProvidersWs('ws://localhost:8546', options);
```

## Usage with Web3

```js
const Web3 = require('web3');
const web3 = new Web3(wsProvider);
```

## Usage with Ethers.js

```js
const ethers = require('ethers');
const provider = new ethers.providers.Web3Provider(wsProvider);
```

Additional client config options can be found [here](https://github.com/theturtle32/WebSocket-Node/blob/v1.0.31/docs/WebSocketClient.md#client-config-options).

## Types

All the TypeScript typings are placed in the `types` folder.

[repo]: https://github.com/ethereum/web3.js
[docs]: http://web3js.readthedocs.io/en/1.0/
