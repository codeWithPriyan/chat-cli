<p align="center">
  <img alt="CLI demo" src="./demos/cli.gif">
</p>

# Table of Contents
   * [Features](#features)
   * [Getting Started](#getting-started)
      * [Prerequisites](#prerequisites)
      * [Usage](#usage)
         * [CLI](#cli)
      * [Using a Reverse Proxy](#using-a-reverse-proxy)
   * [Caveats](#caveats)
   * [Contributing](#contributing)
   * [License](#license)

## Features
- Experimental support for Bing's version of ChatGPT, powered by GPT-4.
- Support for the official ChatGPT raw model, `text-chat-davinci-002`, via OpenAI's API.
- Includes an API server (with Docker support) you can run to use ChatGPT in non-Node.js applications.
- Includes a `ChatGPTClient` and `BingAIClient` class that you can use in your own Node.js applications.
- Includes a CLI interface where you can chat with ChatGPT.
- (`ChatGPTClient`) Replicates chat threads from the official ChatGPT website (with conversation IDs and message IDs), with persistent conversations using [Keyv](https://www.npmjs.com/package/keyv).
  - Conversations are stored in memory by default, but you can optionally [install a storage adapter](https://www.npmjs.com/package/keyv#usage) to persist conversations to a database.
  - The `keyv-file` adapter is also included in this package, and can be used to store conversations in a JSON file if you're using the API server or CLI (see `settings.example.js`).
- (`ChatGPTClient`) Supports configurable prompt prefixes, and custom names for the user and ChatGPT.
  - In essence, this allows you to turn ChatGPT into a different character.
  - This is currently only configurable on a global level, but I plan to add support for per-conversation customization.

## Getting Started

### Prerequisites
- Node.js >= 16.0.0
- npm
- Docker (optional, for API server)
- [OpenAI API key](https://platform.openai.com/account/api-keys)

## Usage

### CLI

#### Setup
Follow the same [setup instructions](#api-server-setup) for the API server, creating `settings.js`.

#### Usage
If installed globally:
```bash
chatgpt-cli
```

If installed locally:
```bash
npm run cli
```

ChatGPT's responses are automatically copied to your clipboard, so you can paste them into other applications.

## Contributing
If you'd like to contribute to this project, please create a pull request with a detailed description of your changes.

## License
This project is licensed under the MIT License.
