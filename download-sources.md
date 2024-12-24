# Download sources

::: warning :construction: WORK IN PROGRESS
This page is a work in progress and is not yet complete.
:::

Download sources are a key component in Hydra. They provide an easy and Steam-like experience to restore games that you have backed up.

## How do download sources works

Hydra by default doesn't come with any download sources, so you have to build one yourself in order to be able to restore your game files within the launcher.

Download sources can be added to Hydra Launcher using a simple JSON structure that will allow you to create a mapping in between the game files and the game titles. You can create and import as many download sources as you want.

::: warning NOTE ON ACCOUNT SYNC
Download sources are not synced to your account due to privacy reasons. If you ever uninstall Hydra, all download sources that you have imported are going to be removed and you have to import them again.
:::

## How to create a download source

A JSON representing a download source has the following structure:

```json
{
  "name": "string",
  "downloads": [
    {
      "title": "string",
      "fileSize": "string",
      "uris": ["string"],
      "uploadDate": "string"
    }
  ]
}
```

### Supported hosters
