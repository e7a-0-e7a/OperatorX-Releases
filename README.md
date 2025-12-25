# OperatorX - Release Repository

This repository contains the compiled releases of the OperatorX plugin for Minecraft servers.

## What is this repository?

This is a **public release repository** that contains only the built JAR files and Maven metadata. The source code is maintained in a separate private repository.

## Installation

### As a Plugin

1. Download the latest `OperatorX-{VERSION}.jar` from the [Releases](https://github.com/e7a-0-e7a/OperatorX-Releases/releases) page
2. Place it in your server's `plugins/` folder
3. Restart your server or use `/reload`

### As a Maven Dependency

Add this repository and dependency to your `pom.xml`:

```xml
<repositories>
    <repository>
        <id>operatorx-releases</id>
        <url>https://raw.githubusercontent.com/e7a-0-e7a/OperatorX-Releases/main</url>
    </repository>
    <repository>
        <id>spigotmc-repo</id>
        <url>https://hub.spigotmc.org/nexus/content/repositories/snapshots/</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>xyz.rhaven</groupId>
        <artifactId>OperatorX</artifactId>
        <version>1.0.0</version>
        <scope>provided</scope>
    </dependency>
</dependencies>
```

## Available Versions

All released versions are available in the Maven repository structure:
- `xyz/rhaven/OperatorX/{VERSION}/OperatorX-{VERSION}.jar`
- `xyz/rhaven/OperatorX/{VERSION}/OperatorX-{VERSION}.pom`
- `xyz/rhaven/OperatorX/{VERSION}/OperatorX-{VERSION}-sources.jar`
- `xyz/rhaven/OperatorX/{VERSION}/OperatorX-{VERSION}-javadoc.jar`

Check the [Releases](https://github.com/e7a-0-e7a/OperatorX-Releases/releases) page for the latest version.

## Maven Repository Structure

```
xyz/
└── rhaven/
    └── OperatorX/
        ├── maven-metadata.xml
        └── {VERSION}/
            ├── OperatorX-{VERSION}.jar
            ├── OperatorX-{VERSION}.pom
            ├── OperatorX-{VERSION}-sources.jar
            ├── OperatorX-{VERSION}-javadoc.jar
            ├── OperatorX-{VERSION}.jar.sha1
            ├── OperatorX-{VERSION}.pom.sha1
            ├── OperatorX-{VERSION}-sources.jar.sha1
            └── OperatorX-{VERSION}-javadoc.jar.sha1
```

## Usage in Your Plugin

Once you've added OperatorX as a dependency, you can use it in your plugin:

```java
import xyz.rhaven.operatorx.OperatorX;
import xyz.rhaven.operatorx.core.Module;
import xyz.rhaven.operatorx.core.BaseModule;

public class MyModule extends BaseModule {
    public MyModule(OperatorX plugin) {
        super(plugin, "MyModule", "1.0.0");
    }
    
    @Override
    protected void registerCommands() {
        registerCommand("mymodule action <arg>");
    }
    
    @Override
    protected void registerPermissions() {
        registerPermission("operatorx.mymodule.action");
    }
    
    @Override
    public boolean handleCommand(CommandSender sender, String action, String[] args) {
        // Your logic here
        return true;
    }
}
```

## Features

- **Modular System**: Easily extensible through modules
- **Core Modules**: Teleport, Homes, Warps, Inventory, Gamemode, Time
- **Add-on System**: External plugins can be registered as modules
- **Permission System**: Integrated permission management
- **Message System**: Configurable messages

## Requirements

- **Minecraft Versions**: 1.21.4+
- **Java Version**: 21
- **Server Types**: Spigot, Paper
- **Dependencies**: Core API (xyz.rhaven:Core:1.0.2)

## Documentation

For detailed API documentation and examples, please refer to the main project documentation (if available) or check the source code.

## Support

- **Website**: https://rhavenside.de
- **Author**: Rhaven
- **Version**: Check the latest release tag

## License

This project is provided as-is. Please refer to the license file for details.

---

**Note**: This repository only contains releases. For issues, feature requests, or contributions, please contact the maintainer through the appropriate channels.

