# PWL

A generic, super-slim password locker for the console written in Python3.  It supports a few different commands (list, add, edit, delete - see ```pwl -h```) and stores all data within an AES blob (EAX mode).

Why did you write this?  What's wrong with [keepassx](https://github.com/keepassx/keepassx) or [pass](https://github.com/zhangkun83/password-store)?

...

## Prerequisites

```
Python 3 stdlib
* argparse
* base64
* os
* secrets
* subprocess 
* time

[pycryptodome](https://www.pycryptodome.org/en/latest/)
* Crypto.Cipher
* Crypto.Random
```

## Installing

1. ```git clone https://github.com/sbassett29/PWL.git```
2. ```pip install pycryptodome``` (if you haven't already)
3. Set ```self.pwl_file_name``` on [line 22](https://github.com/sbassett29/PWL/blob/master/pwl#L22) to a valid file name.  You can run ```pwl -n``` for some suggestions.
4. You'll want to select a random key to use to enc/dec the AES file that ```pwl``` creates.  You can run ```pwl -k``` for some suggestions (base64-encoded random byte strings.)
5. Run ```pwl -h``` for help and options.

## Options

There are a few options, set in the constructor for now (will probably turn into env vars at some point):

1. ```pwl_length``` - must be 16 for now
2. ```pwl_file_name``` - full path of the encrypted file where all data will be stored
3. ```terminal_width``` - must be 120 for now
4. ```col_one_width``` - must be 28 for now
5. ```col_two_width``` - must be 28 for now
6. ```col_three_width``` - must be 60 for now
7. ```enc_dec_key``` - default, unusable value
8. ```encoding``` - utf8 please
9. ```clear_list_time``` - optional time to clear screen after ```pwl -l```, set to 0 or less for more danger
10. ```clear_list_cmd``` - whatever you use to clear your term, default is based upon macos terminal

## Usage

Again, see ```pwl -h```.  But basically, ```pwl -l``` displays the password data to the terminal, ```pwl -a``` and  ```pwl -e``` add and edit data via a few prompts.   And ```pwl -d``` apparently isn't implemented yet :)  Oh, you'll probably want to alias the ```pwl``` file so you don't have to prepend "./" or whatever every time.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/sbassett29/PWL/tags).

## Authors

* **Scott Bassett** - *Initial work* - [sbassett29](https://github.com/sbassett29)

## License

This project is licensed under the CC0 License - see the [LICENSE](LICENSE) file for details.
