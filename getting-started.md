# Getting started

## Prerequisites

- [Node.js](https://nodejs.org/en) version 20 or higher.
- [Python 3.9](https://www.python.org/downloads/release/python-3913/).
- [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable).
- [Git](https://git-scm.com/downloads).

::: warning
We highly recommend you to be double sure that you are running Python 3.9. `libtorrent` is known to have some issues with higher Python versions.
:::

### Additional step for Windows

If you are on Windows, you have to install [OpenSSL 1.1](https://slproweb.com/download/Win64OpenSSL-1_1_1w.exe) which is required by `libtorrent`.

## Cloning the repository

After having all of the prerequisites installed, you should be ready to clone Hydra:

```bash
git clone https://github.com/hydralauncher/hydra.git
```

## Installing dependencies

Once you have cloned the project, you have to install of the required dependencies from both Python and Node.js in order to get it working:

```bash
cd hydra
yarn # To install Node.js dependencies with yarn
pip install -r requirements.txt # To install Python dependencies using pip
```

## Environments

Hydra currently has servers running in two different environments: `staging` and `production`.

`production` is the environment that we use for the release versions of Hydra, and it's stable.
`staging` is the environment that we use for testing. It might be unstable for use, but it's where the bleeding edge features are.

You have to pick one of those environments to run Hydra.

::: tip NOTE ON ACCOUNTS
The user accounts are not shared between environments. Which means that the account that you use for production is not the same that you are going to use for staging.
:::

### Setting up environment variables

You have to set up a few variables in order to select which environment you are going to use. Hydra won't work without those.

| Variable name                          | Value for production                      | Value for staging                         |
| -------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `MAIN_VITE_API_URL`                    | https://hydra-api-us-east-1.losbroxas.org | https://api-staging.hydralauncher.gg      |
| `MAIN_VITE_AUTH_URL`                   | https://auth.hydralauncher.gg             | https://auth-staging.hydralauncher.gg     |
| `MAIN_VITE_CHECKOUT_URL`               | https://checkout.hydralauncher.gg         | https://checkout-staging.hydralauncher.gg |
| `MAIN_VITE_EXTERNAL_RESOURCES_URL`     | https://assets.hydralauncher.gg           | https://assets.hydralauncher.gg           |
| `RENDERER_VITE_EXTERNAL_RESOURCES_URL` | https://assets.hydralauncher.gg           | https://assets.hydralauncher.gg           |
| `MAIN_VITE_WS_URL`                     | wss://ws.hydralauncher.gg                 | wss://ws-staging.hydralauncher.gg         |

Pick one environment to use and place the variables into a `.env` file in the root folder of the project. Like so:

```
# Environment variables for production

MAIN_VITE_API_URL=https://hydra-api-us-east-1.losbroxas.org
MAIN_VITE_AUTH_URL=https://auth.hydralauncher.gg
MAIN_VITE_CHECKOUT_URL=https://checkout.hydralauncher.gg
MAIN_VITE_EXTERNAL_RESOURCES_URL=https://assets.hydralauncher.gg
RENDERER_VITE_EXTERNAL_RESOURCES_URL=https://assets.hydralauncher.gg
MAIN_VITE_WS_URL=wss://ws.hydralauncher.gg
```

### Which environment should you use?

If you are running Hydra from `main` branch, you are good to go with `production` for the most part. If you are running on any other branch, you better off with `staging`.

### Running the project

Once the project setup is done, you can run Hydra using the following script:

```bash
yarn dev
```
