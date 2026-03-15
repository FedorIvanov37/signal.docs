# Command line API

## How to run API in CLI mode 

You can run the Signal API in command-line mode. It can be useful to start the API on remote server where GUI is not 
need

The minimum command to run this mode

``` { .console .signal-console linenums="1" }
signal.exe --console --api-mode

  ::::::::  :::::::::::  ::::::::   ::::    :::      :::      :::
 :+:    :+:     :+:     :+:    :+:  :+:+:   :+:    :+: :+:    :+:
 +:+            +:+     +:+         :+:+:+  +:+   +:+   +:+   +:+
 +#++:++#++     +#+     :#:         +#+ +:+ +#+  +#++:++#++:  +#+
        +#+     +#+     +#+   +#+#  +#+  +#+#+#  +#+     +#+  +#+
 #+#    #+#     #+#     #+#    #+#  #+#   #+#+#  #+#     #+#  #+#
  ########  ###########  ########   ###    ####  ###     ###  ##########

  Simplified ISO generation algorithm v0.20

15.03.2026 11:14:51 [INFO] Press CTRL+C to exit
15.03.2026 11:14:51 [INFO]
15.03.2026 11:14:51 [INFO] ## Begin command line job ID 63e88d3c-15f2-46c5-9a5b-cf8ddeca23ad ##
15.03.2026 11:14:51 [INFO] Signal API running on port 7777. Process ID: 25832
```

After this run command there are two ways only to interact with the Signal API 

* Using the Signal endpoints to get and change the setting, manage the connection, send transactions, and so on 
* Press `CTRL + C` to stop the API

The Signal provides a complete toolkit for full work with API through the endpoint with no interface involving. 
Find latest Postman Collection on [download page](/downloads)

It is also recommended to set [custom config](/data_models/config) up and when needed use dedicated 
[specification file](/data_models/specification) for this mode
