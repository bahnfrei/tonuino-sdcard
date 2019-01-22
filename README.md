# tonuino-sdcard
shell script to manage TonUINO sdcard content, based on ID3v2 tags (if available)

### Dependencies:

* *__id3v2__* tool

### Usage:

    $ tonuino-sdcard [-h] || [-v] -l <path to sdcard> || [-v] [-n] [-r] -c <music folder> <path to sdcard> || -R <path to sdcard>
        -h|--help      show help/usage
        -v|--verbose   show detailed information about executed commands
        -l|--list      list content of sdcard based on ID3v2 tags (if available)
        -c|--copy      copy content of music folder to sdcard, reflecting folder structure and naming convention
        -n|--num       enumerate files mannually (e.g. in case of missing ID3v2 tags or mixed files)
        -r|--replace   replace already existing destination folder
        -R|--reorder   reorder sdcard folders to eliminate gaps

### Examples:

t.b.d.

### Roadmap:

* possibility to add additional files to an existing folder (e.g. to extend a music "playlist")
* ...
