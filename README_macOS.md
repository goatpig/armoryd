# macOS (OS X) README
## Requirements
armoryd is supported on macOS 10.8 and beyond. It is highly recommended to run armoryd on the newest version of macOS that is feasible, as Apple often introduces changes to newer versions that make support of older versions difficult, if not impossible.

Due to [Python](https://python.org/) requirements that can't be met by default on most versions of macOS, it is highly recommended that users use `brew` to install an updated version of Python in order to run armory. Users *must also* install the [Twisted](https://twistedmatrix.com/trac/) library. Please follow these instructions if `brew` is not already on your system.

1. Open a terminal and run the `brew` command. If `brew` isn't found, please execute the following commands from the terminal (aka command line). If the final command returns any errors, consult Google, the *bitcoin-armory* IRC channel on Freenode, or the [Bitcoin Forum](https://bitcointalk.org/index.php?board=97.0) for further instructions. If you're already running Armory on your system, this step shouldn't be necessary.

        /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
        touch ~/.bashrc
        echo "export CFLAGS=\"-arch x86_64\"" >> ~/.bashrc
        echo "export ARCHFLAGS=\"-arch x86_64\"" >> ~/.bashrc
        source ~/.bashrc
        brew update
        brew doctor

2. If everything is successful, execute the following command.

        brew install python2 twisted[tls]

## Downloading and Verifying armoryd
Unlike Armory, there are no formal releases. If tampering is a concern, the user should use Git to obtain the latest version of armoryd. Because of the advanced nature of armoryd, it is assumed that armoryd users are smart enough to use Git and to follow the directions in the Armory repo for verifying Armory.

## Running armoryd
Once the prerequisites have been installed, execute armoryd as described in the [README](README.md). The user will have to compile Armory as described in Armory's macOS README materials.

In order to ensure that the `brew` version of Python is running, execute armoryd using `python2` instead of `python`. The latter may invoke the default version of Python. While this version may work, no guarantees are made.
