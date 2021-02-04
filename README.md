# create-hashes
Create salted and unsalted hashes like MD5, SHA1, SHA256 and more in python.  
This tool is for legal use only! (◔/‿\◔)  
Don't use this tool for illegal activities!  (⋗_⋖)

```bash
  Name            : create-hashes.py
  Created By      : Zumili
  Documentation   : https://github.com/Zumili/create-hashes
  License         : The MIT License
  Version         : 1.0.0
```

## How to install?

`git clone https://github.com/Zumili/create-hashes`

## How to run?

Use internal help for some information.  
`python create-hashes.py -h`

```bash
positional arguments:
  hashtype                  hashtype like: md5, sha1, sha512
  plain                     plain or plain file

optional arguments:
  -h, --help                show this help message and exit
  -a AMOUNT, --amount AMOUNT
                            amount of hashes or salts
  -r, --random              randomize plain or salts
  -l LENGTH, --length LENGTH
                            length of plain
  -s SALT, --salt SALT      use salt and length of salt
  -cp CHARPLAIN, --charplain CHARPLAIN
                            charset of plains
  -cs CHARSALT, --charsalt CHARSALT
                            charset of salts
  -o OUTPUT, --output OUTPUT
                            output file
  -w [WRITE_PLAIN], --write-plain [WRITE_PLAIN]
                            write a separate plain file
  -p, --use-postfix         use salt as postfix
  -n, --no-info             do not print info and hashes
```

Show the available hash types
`python create-hashes.py ?`

Show charsets for plain generation  
`python create-hashes.py -cp ?`

Show charsets for salt generation  
`python create-hashes.py -cs ?`

## Examples

### From external input

Create one single MD5 hash from the plain: password  
`python create-hashes.py md5 password`

Create MD5 hashes from a file filled with plains  
`python create-hashes.py md5 plain.txt`

### Generating plains and salts

Generate a hash from random string using charset [-cp 0] with a length of 8 [-l 8]  
`python create-hashes.py sha1 -cp 0 -l 8`

For more than 1 hash, the option [-a <amount>] is quite useful  
`python create-hashes.py sha256 -cp 0 -l 8 -a 10`

It is also possible to salt these hashes by giving a salt length [-s 6] and a charset for the salt [-cs 2]  
`python create-hashes.py md5 -cp 0 -l 8 -a 10 -s 6 -cs 2`

If salt should be postfix instead of prefix there is option [-p]  
`python create-hashes.py md5 -cp 0 -l 8 -a 10 -s 6 -cs 2 -p`

### Salt the plain lists

To apply 1 random salt with length of 10 [-s 10] to all given plains in file and then hash them  
`python create-hashes.py md5 plain.txt -s 10`

To apply 5 random salts [-a 5] using charset 4 [-cs 4] with length of 8 [-s 8] to all given plains in file in sequential order  
`python create-hashes.py md5 plain.txt -s 10 -cs 4 -a 5`

To randomize the order of the salt option [-r] is available  
`python create-hashes.py md5 plain.txt -s 10 -cs 4 -a 5 -r`

### Write the hashes and plain to files

By using the [-o <file>] option it is possible to store the created hashes to a file. The no output option [-n] suppresses all output  
`python create-hashes.py md5 plain.txt -s 12 -cs 3 -a 5 -n -o hashes.txt`

If a generated plain list is used, it is also possible to store that list with [-w <file>] option  
`python create-hashes.py md5 -a 10 -l 8 -cp 0 -s 6 -cs 4 -o hashes.txt -w generated.txt`

## Version
1.0

## License
[The MIT License](https://opensource.org/licenses/MIT)

## Who?
Written by Zumili ([thomas-messmer.com](http://thomas-messmer.com)) for scientific purposes only.
