# Command line API 

## How to run API in CLI mode 

You can run the Signal API in command-line mode. It can be useful to start the API on a remote server where a GUI is not 
needed

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

After this run command, there are only two ways to interact with the Signal API 

* Using the Signal endpoints to get and change the settings, manage the connection, send transactions, and so on
* Press `CTRL + C` to stop the API
The Signal provides a complete toolkit for working with the API via the endpoint, with no interface involved. 
Find the latest Postman Collection on [download page](/downloads)

It is also recommended to set up a [custom config](/data_models/config) and, when needed, use a dedicated 
[specification file](/data_models/specification) for the API mode
