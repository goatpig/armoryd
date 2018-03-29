# armoryd

**Created by Alan Reiner on 13 July, 2011**

**Forked by goatpig in February 2016**

[armoryd](https://github.com/goatpig/armoryd) is a JSON-RPC daemon for [Armory](https://github.com/goatpig/BitcoinArmory). armoryd allows users to use Armory functionality solely from a command line or via JSON-RPC, write scripts that implement Armory functionality, etc. armoryd relies on a client/server model. If armoryd is not already running on a computer, the first instance will place armoryd in server mode. Once armoryd is running, users may send commands to the armoryd server via JSON. If the user doesn't have a JSON client, a second instance of armoryd may be used to send the commands.

To operate armoryd, copy the following files into the Armory root folder:

- armoryd.py
- txjsonrpc/*.*

As an alternative, copy the following files from the Armory project into armoryd's root folder:

- CppBlockUtils.py and \_CppBlockUtils.pyd/so (both files created in Armory's root directory when compiling Armory).
- All files in the Armory's *armoryengine* subdirectory.

In order to run armoryd, the user must have [bitcoind](https://en.bitcoin.it/wiki/Bitcoind) installed on the same computer as armoryd. As of Jan. 2018, bitcoind can be downloaded in binary form for Windows and Linux, alongside Bitcoin Core downloads, while OS X users must build and install their own binaries. Go to [the Bitcoin Core repository](https://github.com/bitcoin/bitcoin) for more information on how to download, build and install the bitcoind code for the branch or tag you wish to use.

In addition, armoryd requires `ArmoryDB`, a binary built when compiling Armory. Therefore, while Armory need not run in order to run armoryd, one must compile Armory in order to obtain the ArmoryDB binary.

## Dependencies

* ArmoryDB - Database that reads the Bitcoin blockchain
 Source: https://github.com/goatpig/BitcoinArmory  (Be sure to install Armory dependencies too)
 Detailed documentation: https://github.com/goatpig/BitcoinArmory/blob/master/README_ArmoryDB.md

* Python Twisted - Asynchronous networking package
 Linux:   Install package `python-twisted`
 Windows: [Download](https://twistedmatrix.com/trac/wiki/Downloads)
 macOS:   See [README_macOS.md](README_macOS.md) for more info.
 
## Usage

After obtaining a compiled version of Armory, the user must invoke the ArmoryDB binary in order to use armoryd, in addition to running bitcoind. Please see the ArmoryDB README in the Armory repo for more detailed information regarding how to invoke Armory.

Upon startup, armoryd will attempt to load all wallets and lockboxes in the default Armory data directory or, if overridden by the "--datadir=X" argument, a user-defined directory.

The following are some examples of how to invoke armoryd. Note that armoryd has access to all command line flags used by Armory.

**--SERVER--**
* `python armoryd.py` - Run an armoryd server on mainnet.
* `python armoryd.py --testnet` - Run an armoryd server on testnet.
* `python armoryd.py --datadir=/home/snakamoto/Armory_Wallets` - Run armoryd with wallets and lockboxes loaded from a non-standard location.

**--CLIENT--**
* `python armoryd.py getwalletinfo` - Receive info about the mainnet wallet that is currently active on the armoryd server.
* `python armoryd.py getarmorydinfo` - Get information about the server version of armoryd that is currently running.
* `python armoryd.py getarmoryfunctions` - Get a list of functions available on the armoryd server.
* `python armoryd.py watchwallet sender@c.net watchCmd=remove` - Stop sending e-mail notifications from a given e-mail address.
* `python armoryd.py --testnet createustxtoaddress n3QJ7oiaDHBMxtN5bckLDLBr98zeufEkMv 10` - Create an unsigned transaction of 10 BTC to be sent to the given address on testnet. armoryd will automatically determine which coins to use from the loaded wallet/lockbox.

**Please note that Armory and armoryd should not be run at the same time!!!** Any attempt to run both programs at the same time could lead to unpredictable behavior, including wallet and lockbox corruption.

## License

Distributed partially under the GNU Affero General Public License (AGPL v3) and the MIT License. See the [LICENSE file](LICENSE) for more information.

## Copyright

Copyright (C) 2011-2015 Armory Technologies, Inc.
Copyright (C) 2016-2018 goatpig
