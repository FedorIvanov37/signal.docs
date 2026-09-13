# Command line API 

## How to run API in CLI mode 

You can run the Signal API in command-line mode. This is useful on a remote server where a GUI is not 
needed.

The simplest command to start this mode is:

```text {.signal-console linenums=1}
C:\signal>signal.exe --console --api-mode

  ::::::::  :::::::::::  ::::::::   ::::    :::      :::      :::
 :+:    :+:     :+:     :+:    :+:  :+:+:   :+:    :+: :+:    :+:
 +:+            +:+     +:+         :+:+:+  +:+   +:+   +:+   +:+
 +#++:++#++     +#+     :#:         +#+ +:+ +#+  +#++:++#++:  +#+
        +#+     +#+     +#+   +#+#  +#+  +#+#+#  +#+     +#+  +#+
 #+#    #+#     #+#     #+#    #+#  #+#   #+#+#  #+#     #+#  #+#
  ########  ###########  ########   ###    ####  ###     ###  ##########

  Simplified ISO generation algorithm v0.21

15.03.2026 20:13:55 [INFO] Press CTRL+C to exit
15.03.2026 20:13:55 [INFO]
15.03.2026 20:13:55 [INFO] ## Begin command line job ID 79085d6c-d0ac-405e-98a6-05c7456ae01d ##
15.03.2026 20:13:55 [INFO] Signal API running on port 7777. Process ID: 14976
```

Once the API is running, you can interact with it in two ways: 

* Use the Signal endpoints to read and change settings, manage the connection, send transactions, and perform other operations
* Press `CTRL + C` to stop the API
Signal provides a complete set of endpoints for working with the API without a graphical interface. 
Find the latest Postman collection on the [download page](/downloads).

It is also recommended to set up a [custom config](/data_models/config) and, when needed, use a dedicated 
[specification file](/data_models/specification) for API mode.
