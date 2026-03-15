# Command line API

## How to run API in CLI mode 

You can run the Signal API in command-line mode. It can be useful to start the API on remote server where GUI is not 
need

The minimum command to run this mode

```text {.signal-console linenums=1}
C:\signal>signal.exe --console --api-mode

  ::::::::  :::::::::::  ::::::::   ::::    :::      :::      :::
 :+:    :+:     :+:     :+:    :+:  :+:+:   :+:    :+: :+:    :+:
 +:+            +:+     +:+         :+:+:+  +:+   +:+   +:+   +:+
 +#++:++#++     +#+     :#:         +#+ +:+ +#+  +#++:++#++:  +#+
        +#+     +#+     +#+   +#+#  +#+  +#+#+#  +#+     +#+  +#+
 #+#    #+#     #+#     #+#    #+#  #+#   #+#+#  #+#     #+#  #+#
  ########  ###########  ########   ###    ####  ###     ###  ##########

  Simplified ISO generation algorithm v0.20

15.03.2026 20:13:55 [INFO] Press CTRL+C to exit
15.03.2026 20:13:55 [INFO]
15.03.2026 20:13:55 [INFO] ## Begin command line job ID 79085d6c-d0ac-405e-98a6-05c7456ae01d ##
15.03.2026 20:13:55 [INFO] Signal API running on port 7777. Process ID: 14976
```

After this run command there are two ways only to interact with the Signal API 

* Using the Signal endpoints to get and change the setting, manage the connection, send transactions, and so on 
* Press `CTRL + C` to stop the API

The Signal provides a complete toolkit for full work with API through the endpoint with no interface involving. 
Find latest Postman Collection on [download page](/downloads)

It is also recommended to set [custom config](/data_models/config) up and when needed use dedicated 
[specification file](/data_models/specification) for this mode
