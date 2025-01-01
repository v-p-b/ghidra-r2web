GhidraR2Web Plugin
==================

This is the original `ghidra-r2web` script refactored into a Ghidra module. Implementation is mostly taken as-is in the hope that fixes will be easier in the new code structure, any feedback is appreciated (please use the Issue tracker)!


Build
-----

SDKMan environment configuration is provided.

```
export GHIDRA_INSTALL_DIR=/path/to/ghidra
gradle buildExtension
```

The extension .zip will be created in `dist/`.


Install
-------

In **Ghidra Project Manager** choose `File->Install Extensions`. In the top right corner of the new window click the green plus sign, and choose the distribution ZIP. Restart Ghidra as instructed.

After restart open the **Code Browser**, that should offer you to configure the new extension. Accept and tick the checkbox next to the plugin name. If this option is not offered you can use the `File->Configure` menu item, then click the Configure link under Ghidra Core to navigate to the same GUI for enabling the plugin.


Usage
-----

The plugin registers a new menu item under the Tools menu of Ghidra's Code Browser to start/stop the embedded web server. From there you can use r2's connection syntax as described in the original README. 

### Headless

The Python script provided in the `ghidra_scripts` directory intializes the r2web server on port 9191. You should provide this script as `-postScript` when launching headless Ghidra.
