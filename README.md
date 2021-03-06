# Address Library Database
The Address Library Database helps facilitate the sharing of function and static variable names between Skyrim Anniversary Edition (version 1.6+) IDA databases. It is loaded by the Address Library Manager that is distributed in the `resources` channel of the `SkyrimSE RE` Discord server. Multiple versions of the game are supported by taking advantage of the identifiers used by the [Address Library](https://www.nexusmods.com/skyrimspecialedition/mods/32444).

To load a database you require a `relib` file and a `rename` file in the same directory with the same name. The `relib` file contains a list of identifiers and their respective offsets for each version of the game. The `rename` file contains a list of identifiers and their names.

When a database is loaded, each version of the game that the `relib` file supports will be listed. You can then select a version of the game and dump its identifier and offset pairs to assist with plugin development, or create the Address Library for either that specific version of the game or all supported versions of the game.

## Importing
To import identifier and name pairs to your database, you must first export offset and name pairs from your IDA database. This is done by running either the `IDAExportNames_IDA6.py` script or the `IDAExportNames_IDA7.py` script in IDA, depending on the version of IDA you are using. The `idanames.txt` file will then be created, which can be imported using the Address Library Manager. First select `Names` and then click `Import from IDA script result`. Then select the version of the game that was used to create your IDA database. The identifier and name pairs will then be added to your `rename` file.

## Exporting
To export offset and name pairs from your database you first select `Names` and then click `Export names to IDA 6.x` or `Export names to IDA 7.x`, depending on the version of IDA you are using. Then select the version of the game that was used to create your IDA database. Optionally, to export only the names from the database that have been changed, specify an `idanames.txt` file to serve as a point of comparison. The `SetNamesInIDA.py` script will then be created, which can be run in IDA.
