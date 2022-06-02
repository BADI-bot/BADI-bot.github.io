---
title: "Configuration"
draft: false
type: docs
categories:
    - Documentation
tags:
    - "Configuration"
---

## Configuration File

The configuration for MoDiBo lives in `config.json` in the root directory of the project (parent to `src/`). There is no separate configuration file loaded when MoDiBo is run in testing mode, but a separate `.env.testing` is used.

### Additional Environment Variables

Some configuration lives in a `.env` file. To set this up, simply
1. Make a copy of `.env.template`
2. Rename it to `.env` (or `.env.testing` for testing mode)
3. Set the variables as appropriate

### Generate Configuration File

To generate a configuration file with the default settings, run `npm run resetConfig`. 

**NOTE:** This will overwrite your existing configuration if it exists, so use with caution!

## View Default Configuration

To view the default configuration without generating a configuration file, run `npm run showDefaultConfig`. This will log the default configuration as a warning.

## Configuration Options

### `prefix`
The character(s) to appear at the beginning of a message to register a command.

**Default:**
```json
"prefix": "$"
```

### `activity`
The text to display in the online user list as the current status of the bot. This option has two keys:

- `"type"`: The activity type, which precedes the description. Must be one of (case insensitive)
    - `PLAYING`
    - `STREAMING`
    - `LISTENING`
    - `WATCHING`
    - `COMPETING`
- `"description"`: The text that appears after the activity type.

**Default:**
```json
{
    "type": "playing",
    "description": "$help"
}
```

### `color`
The default color for message embeds created with the `utils`. Must be one of the colors defined in `utils.js`, case insensitive. Those are currently

-  <span style="display:inline-block;background-color:#510c76;color: white;padding:5px;margin-bottom:5px">PURPLE</span>
-  <span style="display:inline-block;background-color:#fc0004;color: white;padding:5px;margin-bottom:5px">RED</span>
-  <span style="display:inline-block;background-color:#00fc00;color: black;padding:5px;margin-bottom:5px">GREEN</span>

**Default:**
```json
"color": "purple"
```

### `plugins`
An object of objects. The key should be the slug of a plugin installed to the `plugins/` directory. The options within, if any, should follow the specifications of that specific plugin's documentation.

**Example:**
```json
{
    "example-plugin": {},
    "example-plugin-with-options": {
        "option1": "value",
        "option2": true
    }
}
```

**Default:**
```json
{}
```

### `discordLogging`
Configuration for logging to Discord via the Winston library. This option has two keys:

- `"active"`: Boolean value for if Discord logging should be enabled. If `true`, messages will be logged to Discord.
- `"level"`: The logging level where messages should start logging to Discord. Messages at this level and more severe will be logged. From most severe to least severe, the log levels are
    - `error`
    - `warn`
    - `info`
    - `verbose`
    - `debug`
    - `silly`

**NOTE:** For fully functioning Discord logging, a valid Webhook URL must be provided in the `.env` file.

**Default:**
```json
{
    "active": true,
    "level": "warn"
}
```