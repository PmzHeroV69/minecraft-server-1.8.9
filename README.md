# Minecraft Server 1.8.9

Gradle build setup for minecraft 1.8.9 server. (there is no server source code)

## How to get the Source Code
to compile minecraft, you obviously need the source code. to get the code you need to decompile
minecraft server 1.8.9 jar from https://mcversions.net/download/1.8.9.
to decompile the jar using mcp (using fernflower) you need to first download mcp 1.8.8 from http://www.modcoderpack.com/

then put the server jar in the `mcp/jars` folder. then name the jar to `minecraft_server.jar`.
make sure your java version is 8 and run `./decompile.sh` for linux and `decompile.bat` for windows (requires python2, modify the script to execute python2).

you might also need to have the client installed so it will also decompile the client. after it decompiled, you can copy the `net` folder in `mcp/src/minecraft_server` 

and paste it in your project src directory (`/src/java`). do not touch netty and guava versions in `build.gradle` because it causes problems and minecraft code uses those versions.

if you found any higher version of guava or netty that supports minecraft's code, feel free to open a pull request or issue

## Building

You can use `./gradlew shadowjar` to compile the server. After the compilation process, you should be able to find the
compiled jar file in `build/libs` directory. Using Java 8 is Recommended.
