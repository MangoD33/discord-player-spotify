# Spotify Extractor (metadata only)

This is a reworked Spotify extractor inspired from the original one at @discord-player/extractors.

## Installation

```bash
npm install discord-player-spotify
```

## Usage

```js
const { Player } = require("discord-player");

const { SpotifyExtractor } = require("discord-player-spotify");
// Or
import { SpotifyExtractor } from "discord-player-spotify";

const player = new Player(client, {});

await player.extractors.register(SpotifyExtractor, { 
    clientId: "your-client-id",
    clientSecret: "your-client-secret",
 });
```

## Options

| Option | Type | Default | Required | Description |
| --- | --- | --- | --- | --- |
| clientId | string | null | Yes | Your Spotify client id |
| clientSecret | string | null | Yes | Your Spotify client secret |
| market | string | US | No | The market to use for the Spotify API. |
| createStream(ext: SpotifyExtractor, url: string) => Promise<Readable \| string>; | function | null | No | A function that returns a Readable stream or a string URL to the stream. |

[Information on the market parameter and the reason why it is required.](https://developer.spotify.com/documentation/web-api/concepts/track-relinking)

[How to get the spotify client id and secret.](https://developer.spotify.com/documentation/web-api/concepts/apps)

> You can also set clientId and clientSecret in the environment variables `DP_SPOTIFY_CLIENT_ID` and `DP_SPOTIFY_CLIENT_SECRET`.