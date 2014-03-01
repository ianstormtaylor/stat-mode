stat-mode
=========
### Offers convenient getters and setters for the stat `mode`

You know that `mode` property on the `fs.Stat` object that you probably
usually just ignore? Well there's acutally a lot of information packed
into that number. This module helps you extract that information.

All the getters are also setters, which change the `mode` property
appropriately. This is useful for when you have to build up your
own `fs.Stat` object for whatever reason (like when implementing a
FUSE filesystem.


Installation
------------

``` bash
$ npm install stat-mode
```


Example
-------

So given some arbitrary file (let's say `/bin/echo`):

``` bash
$ ls -l /bin/echo
-rwxr-xr-x 1 root wheel 14128 Aug 11  2013 /bin/echo
```

``` javascript
var fs = require('fs');
var Mode = require('stat-mode');


```


API
---

### new Mode(Object stat) → Mode

You must pass in "stat" object to the `Mode` constructor. The "stat"
object can be a real `fs.Stat` instance, or really any Object with a
`mode` property.

#### mode.isDirectory([Boolean set]) → Boolean

Returns `true` if the mode's file type is "directory", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "directory".

#### mode.isFile([Boolean set]) → Boolean

Returns `true` if the mode's file type is "file", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "file".

#### mode.isBlockDevice([Boolean set]) → Boolean

Returns `true` if the mode's file type is "block device", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "block device".

#### mode.isCharacterDevice([Boolean set]) → Boolean

Returns `true` if the mode's file type is "character device", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "character
device".

#### mode.isSymbolicLink([Boolean set]) → Boolean

Returns `true` if the mode's file type is "symbolic link", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "symbolic link".

#### mode.isFIFO([Boolean set]) → Boolean

Returns `true` if the mode's file type is "FIFO", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "FIFO".

#### mode.isSocket([Boolean set]) → Boolean

Returns `true` if the mode's file type is "socket", `false` otherwise.
If you pass `true` to the function, then the mode will be set to "socket".

#### mode.owner.read → Boolean [Getter/Setter]

`true` if the mode is "owner read" rights, `false` otherwise.

#### mode.owner.write → Boolean [Getter/Setter]

`true` if the mode is "owner write" rights, `false` otherwise.

#### mode.owner.execute → Boolean [Getter/Setter]

`true` if the mode is "owner execute" rights, `false` otherwise.

#### mode.group.read → Boolean [Getter/Setter]

`true` if the mode is "group read" rights, `false` otherwise.

#### mode.group.write → Boolean [Getter/Setter]

`true` if the mode is "group write" rights, `false` otherwise.

#### mode.group.execute → Boolean [Getter/Setter]

`true` if the mode is "group execute" rights, `false` otherwise.

#### mode.others.read → Boolean [Getter/Setter]

`true` if the mode is "others read" rights, `false` otherwise.

#### mode.others.write → Boolean [Getter/Setter]

`true` if the mode is "others write" rights, `false` otherwise.

#### mode.others.execute → Boolean [Getter/Setter]

`true` if the mode is "others execute" rights, `false` otherwise.