# PWL

A generic password locker for the console written in Python3.  It supports a few different commands (list, add, edit, delete - see ```./pwl -h```) and stores all data within an AES blob (EAX mode).

Why did you write this?  What's wrong with ```keepass``` or ```pass```?

...

### Prerequisites

```
Python 3 stdlib
* argparse
* base64
* os
* secrets

pycrypto
* Crypto.Cipher
* Crypto.Random 
```

### Installing

1. ```git clone https://github.com/sbassett29/PWL.git```
2. Set ```self.pwl_file_name``` on [line 22](https://github.com/sbassett29/PWL/blob/master/pwl#L22).  You can use the ```suggest_pwl_file_names``` helper function to suggest random file names.
3. You'll want to select a random key to use to enc/dec the AES file that ```pwl``` creates.  Using the ```base64``` of ```get_random_bytes(16)``` should work alright.
4. Run ```./pwl -h``` for help and options.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags).

## Authors

* **Scott Bassett** - *Initial work* - [sbassett29](https://github.com/sbassett29)

## License

This project is licensed under the CC0 License - see the [LICENSE](LICENSE) file for details.
