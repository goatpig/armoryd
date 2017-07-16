# armoryd

**Created by Alan Reiner on 13 July, 2011**

**Forked by goatpig in February 2016**

[armoryd](https://github.com/goatpig/armoryd) is a JSON-RPC daemon for Bitcoin Armory (https://github.com/goatpig/BitcoinArmory)

To operate armoryd, copy the following files into the Bitcoin Armory root folder:

- armoryd.py
- txjsonrpc/*.*

Or copy the following files from the Bitcoin Armory project into armoryd's root folder:

- CppBlockUtils.py and _CppBlockUtils.pyd/so (results from building BitcoinArmory Windows/*nix)
- /armoryengine/*.*

### Dependencies

* BitcoinArmory 
Source: https://github.com/goatpig/BitcoinArmory

* Python Twisted -- asynchronous networking  
 Linux:   Install package `python-twisted`  
 Windows: [Download](https://twistedmatrix.com/trac/wiki/Downloads)  

## License

Distributed partially under the GNU Affero General Public License (AGPL v3)  
and the MIT License
See [LICENSE file](LICENSE)

## Copyright

Copyright (C) 2011-2015, Armory Technologies, Inc.
