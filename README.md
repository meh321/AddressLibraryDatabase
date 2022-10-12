# Address Library Database
The Address Library Database helps facilitate the sharing of function and static variable names between Skyrim Anniversary Edition IDA databases. It is loaded by the Address Library Manager that is distributed in the `resources` channel of the `SkyrimSE RE` Discord server. Game versions 1.6.317.0 and above are supported by assigning names to [Address Library](https://www.nexusmods.com/skyrimspecialedition/mods/32444) identifiers.

The Address Library Database consists of a `relib` file and a `rename` file. The `relib` file contains a list of identifiers and their paired offsets for each version of the game, and the `rename` file contains a list of identifiers and their paired names.

When a `relib` file and a `rename` file have been loaded, each version of the game that the `relib` file supports will be listed. You can then select a version of the game and dump its identifier and offset pairs to assist with plugin development, or create the Address Library for either that specific version of the game or all supported versions of the game.

## Importing to the Address Library Database
Export offset and names pairs from your IDA database to the `IDANames.txt` file by running either the `IDAExportNames_IDA6.py` script or the `IDAExportNames_IDA7.py` script in IDA, depending on the version of IDA you are using. Before running the script, the `GetFilePath` function must be edited to return the directory in which the `IDANames.txt` file will be created. The `IDANames.txt` file can then be imported using the Address Library Manager by selecting `Names`, clicking `Import from IDA script result`, and then selecting the version of the game that was used to create your IDA database.

## Exporting to your IDA database
Export offset and name pairs from the Address Library Database by selecting `Names` and clicking `Export names to IDA 6.x` or `Export names to IDA 7.x`, depending on the version of IDA you are using. Then select the version of the game that was used to create your IDA database. Optionally, to export only the names from the Address Library Database that have been changed, specify an `IDANames.txt` file to serve as a point of comparison. The `SetNamesInIDA.py` script will then be created in the same directory as the Address Library Manager, which must then be run in IDA.
