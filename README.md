# voltscript-console-colors
Constants for manipulating colours on Terminal etc. For further details, see https://learn.microsoft.com/en-us/windows/console/console-virtual-terminal-sequences#text-formatting. The format is ESC character (ASCII character 27) + "[" + number + "m".

This requires support for colorizing text in the relevant console being used. Not all terminal programs support this. Where unsupported, the character sequence for the formatting will be outputted instead. Obviously, changing color is unsupported when writing to log files.

Some terminals (e.g. Visual Studio Code) will enforce foreground color based on background, presumably to prevent accessibility violations.

## Using dependency management

Dependency management is available in the documentation for each project, but also aggregated here:

### Authentication

You'll need a [Personal Access Token](https://help.hcltechsw.com/docs/voltscript/early-access/howto/writing/archipelago.md#github-personal-access-token) to use GitHub REST APIs. You'll then need to add this to the JSON object in your [atlas-settings.json](https://help.hcltechsw.com/docs/voltscript/early-access/howto/writing/archipelago.md#atlas-settingsjson), in the .vss directory of your user home directory:

```json
    "hcl-github": {
        "type": "github",
        "token": "${env.TOKEN}"
    }
```

### Repository

You'll need to add to your **repositories** object in the atlas.json of your project:

```json
        {
            "id": "hcl-github",
            "type": "github",
            "url": "https://api.github.com/repos/HCL-TECH-SOFTWARE"
        }
```

### Dependency

You'll need the relevant dependency to add to your **dependencies** or **testDependencies** object in the atlas.json of your project:

```json
        {
            "library": "voltscript-console-colors",
            "version": "1.0.1",
            "module": "VoltScriptConsoleColors.vss",
            "repository": "hcl-github"
        }
```

## Contributing

See [CONTRIBUTING.md](contributing.md).

## Code of Conduct

See [CODE_OF_CONDUCT.md](code_of_conduct.md).

## Issues and discussions

Let's chat on [OpenNTF Discord](https://openntf.org/discord).

For long-running discussions, use Discussions area in GitHub. For bugs and feature requests **specific to VoltScript Testing Framework** use, Issues area.