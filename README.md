# Lindholm

Lindholm automates your Overwatch custom game, letting you provide a quality server without constant manual intervention.  
At this time, Lindholm can:
- Launch Overwatch and set up your custom game server.
- Detect team size imbalances and autobalance.
- Skip post game screens.
- Scramble teams.  

With more features in development, including custom map rotations, discord integration, game logging and analytics.

## Getting Started

These instructions will get Lindholm configured on your system and running your server.

### Prerequisites

- Only been tested on Windows 10, and is unlikely to work on other operating systems.
- Battlenet, and Overwatch.
- At least one custom game preset saved in Overwatch for automatic setup.
- Optionally an alternate Battlenet account with Overwatch, if you wish to play while the server is running.
- Optionally a Windows virtual machine. Some systems will require Overwatch be the active window while Lindholm is running, making the computer effectively unusable without a virtual machine.

### Installing

Click "Clone or Download" -> Download Zip  

Extract files anywhere.

Src folder can safely be deleted, but is present if you want to see or modify the code.

### Configuration

Open cfg.yaml in a text editor such as notepad.

Ensure the elements marked "REQUIRED" are correct.

```BattlenetExecutableFilePath``` must be an absolute path to your Battle.net.exe.
This should usually be ```C:\Program Files (x86)\Battle.net\Battle.net.exe```

```OverwatchSettingsFilePath``` must be an absolute path to your Overwatch Settings_v0.ini
This should usually be ```C:\Users\YOUR_USER\Documents\Overwatch\Settings\Settings_v0.ini``` where "YOUR_USER" is your user folder.
If it is present at that location, leave ```OverwatchSettingsFilePath``` commented out ("#" symbol to the far left).
If it is not present at that location, remove the "#" symbol on the line, and replace the value with the correct path.

```ServerName``` is the name your server will be given. 
Blizzard blocks certain names based on length and keywords. If your name doesn't load properly, try using a different name.

```PresetLocation``` is the preset that will be loaded when your custom game is started.
Presets are numbered starting with 0, in reading order.
Preset buttons come in rows of 4 in the preset menu, so the layout looks like:
0  1  2  3  
4  5  6  7  
8  9  10 11  
etc.  
**Important Note:** This feature is unstable, and may fail to load a preset or load an incorrect preset at times. 
Consider manually verifying the preset was correctly loaded, or setting up the server preset manually and then starting Lindholm.
Manually verifying the preset can be made easier by using a unique number of spectator slots in the preset.
See "Correcting Errors"

### Running Lindholm

Lindholm can be run in two ways, for convenience.

#### Full Setup Run

This run is triggered when Lindholm is launched while Overwatch is closed.
This will launch Overwatch, set up your custom game, and run the game.
1. Configuration must be complete.  
2. Overwatch must be closed.  
3. Launch Lindholm.exe

#### Existing Server Run

This run is triggered when Lindholm is launched while Overwatch open.
This run assumes a server is already set up, properly configured, and running.
This lets you stop and restart the bot without needing to repeat server setup.

1. Configuration must be complete.
2. Overwatch must be open, with a custom server running.
3. Overwatch must be at the server's lobby screen.
3. **Overwatch must have contrast set to minimum in settings.** This is set automatically during the Full Setup Run.


## Correcting Errors

Lindholm can and likely will fail at some point. Unpredictable menu load times and translucent menus lead can cause a variety of problems.
If you find Lindholm sitting somewhere other than the Lobby screen: 
1. Close Lindholm (the command window, not Overwatch)
2. Fix any issues caused (usually none).
3. Navigate back to the lobby screen.
4. Launch Lindholm, which will start using the Existing Server Run execution.
We are working to improve stability in these cases.

If you find Lindholm has added too many bots (a result of failing to remove bots), you may choose not to intervene.  
This problem is usually fixed at the beginning of a new match, or when more players join.

## FAQ

- #### Overwatch looks grey?  
Lindholm requires Overwatch's contrast to be set to minimum to see properly, and automatically sets the contrast when it launches Overwatch.  
You can set the contrast back to normal in Overwatch's settings.

## Built With

* [Overwatch-Custom-Game-Automation](https://github.com/ItsDeltin/Overwatch-Custom-Game-Automation) - Makes interfacing with Overwatch custom games possible.

## Authors

* **Deltin** - *Overwatch custom game interfacing* - [Github](https://github.com/ItsDeltin) - [Website](https://www.abyxa.net/)
* **Qazzquimby** - *Server level work* - [Github](https://github.com/Qazzquimby)

## Contributing

Not organized yet. Consider creating an issue or contacting me [here](https://discord.gg/XdfYVr9)


## License

This project is licensed under the MIT License.
