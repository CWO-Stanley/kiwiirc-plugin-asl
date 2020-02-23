# Custom Startup for [Kiwi IRC] (https://kiwiirc.com)

This plugin creates a customised startup screen for age/sex/location based off Welcome.vue

It then display's this data in a customised userbox based off UserBox.vue

It also provides a nicklist style user list with search/filter for users to find other chatters

#### Dependencies
* node (https://nodejs.org/)
* yarn (https://yarnpkg.com/)

#### Building and installing

1. Build the plugin

   ```console
   $ yarn
   $ yarn build
   ```

   The plugin will then be created at `dist/plugin-asl.js`

2. Copy the plugin to your Kiwi webserver

   The plugin file must be loadable from a webserver. Creating a `plugins/` folder with your KiwiIRC files is a good place to put it.

3. Add the plugin to KiwiIRC

   In your kiwi `config.json` file, find the `plugins` section and add:
   ```json
   {"name": "asl", "url": "/plugins/plugin-asl.js"}
   ```

   To enable the startup screen, tell KiwiIRC to use the startup screen from the plugin. Set `"startupScreen"` to `plugin-asl`.

#### Configuration

```
"plugin-asl" : {
    "gecosType": 1,
    "showRealname": false,
    "showUserBrowser": true,
    "userBrowserIcon": "fa-heart",
    "singleLineUserbox": false,
    "singleLineString": {
        "age": "%a years",
        "sex": "%s",
        "location": "%l",
        "separator": " ",
    },
    "ageRanges": [
        { "name": "All", "value": "all" },
        { "name": "< 25", "value": "<25" },
        { "name": "25 - 45", "value": "25-46" },
        { "name": "> 45", "value": ">45" },
    ],
    "sexes": {
        "Male": { "chars": "M", "colour": "#00F" },
        "Female": { "chars": "F", "colour": "#F0F" },
        "Other": { "chars": "O", "colour": "#0F0" },
    },
    "queryKeys": {
        "age": "age",
        "sex": "sex",
        "location": "location",
        "realname": "realname",
    },
    "strings": {
        "age": "Age",
        "sex": "Sex",
        "location": "Location",
        "realname": "Real Name",
        "info": "Info",
        "browseUsers": "Browse Users",
    }
},
```

## License

[Licensed under the Apache License, Version 2.0](LICENSE).
