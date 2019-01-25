# tonuino-sdcard
shell script to manage TonUINO sdcard content, based on ID3v2 tags (if available)

### Dependencies:

* *__id3v2__* tool

### Usage:

    $ tonuino-sdcard [-h] || [-v] -l <path to sdcard> || [-v] [-n] [-a] [-r] -c <music folder> <path to sdcard> || -R <path to sdcard>
        -h|--help      show help/usage
        -v|--verbose   show detailed information about executed commands
        -l|--list      list content of sdcard based on ID3v2 tags (if available)
        -c|--copy      copy content of music folder to sdcard, reflecting folder structure and naming convention
        -n|--num       enumerate files mannually (e.g. in case of missing ID3v2 tags or mixed files)
        -a|--add       add files to an existing folder (implies parameter -n, enumerate files mannually)
        -r|--replace   replace already existing destination folder
        -R|--reorder   reorder sdcard folders to eliminate gaps

### Examples:

copy to sdcard

    $ tonuino-sdcard -c Music/WasIstWas/DieSterneUndDieZeit /Volumes/TonUINO
    $ tonuino-sdcard -c Music/KOKOSNUSS/Kokosnuss\ und\ die\ Wetterhexe/ /Volumes/TonUINO

copy to sdcard and show details/be verbose

    $ tonuino-sdcard -c Music/Der\ Traumzauberbaum/ /Volumes/TonUINO -v
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_18_-_Mondsilbertaufe.mp3 /Volumes/TonUINO/03/018.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_08_-_Frühlingslied.mp3 /Volumes/TonUINO/03/008.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_12_-_Lied_Von_Der_Anstrengung,_Böse_Zu_Sein.mp3 /Volumes/TonUINO/03/012.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_15_-_Wie_Riesen_Niesen.mp3 /Volumes/TonUINO/03/015.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_11_-_Kleine_Wolke.mp3 /Volumes/TonUINO/03/011.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_09_-_Ich_Bin_Doch_Kein_Schneemann.mp3 /Volumes/TonUINO/03/009.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_16_-_Klopsemops.mp3 /Volumes/TonUINO/03/016.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_04_-_Der_Eierbecher.mp3 /Volumes/TonUINO/03/004.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_14_-_Regenlied.mp3 /Volumes/TonUINO/03/014.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_17_-_Das_Bächlein.mp3 /Volumes/TonUINO/03/017.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_03_-_Der_Pfannkuchenschreck.mp3 /Volumes/TonUINO/03/003.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_06_-_Liebkoselied.mp3 /Volumes/TonUINO/03/006.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_19_-_Eine_Kleine_Stadt.mp3 /Volumes/TonUINO/03/019.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_05_-_Gespensterduett.mp3 /Volumes/TonUINO/03/005.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_20_-_Traumreise.mp3 /Volumes/TonUINO/03/020.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_02_-_Küsschenlied.mp3 /Volumes/TonUINO/03/002.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_01_-_Traumzauberbaum.mp3 /Volumes/TonUINO/03/001.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_10_-_Frosch-Rock'n'Roll.mp3 /Volumes/TonUINO/03/010.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_13_-_Neidlied.mp3 /Volumes/TonUINO/03/013.mp3 ... DONE
    cp Music/Der Traumzauberbaum//Reinhard_Lakomy_&_Monika_Ehrhardt_-_Der_Traumzauberbaum_-_07_-_Mary_Lu.mp3 /Volumes/TonUINO/03/007.mp3 ... DONE

copy to sdcard and enumerate manually (e.g. songs from different albums could have the same track number and would therefore be overwritten)

    $ tonuino-sdcard -c Music/Lieblingslieder /Volumes/TonUINO -n

show sdcard content nicely (using system tool)

    $ tree /Volumes/TonUINO
    /Volumes/TonUINO
    ├── 01
    │   ├── 001.mp3
    │   ├── 002.mp3
    │   ├── 003.mp3
    │   ...
    │   └── 025.mp3
    ├── 02
    │   ├── 001.mp3
    │   ├── 002.mp3
    │   ├── 003.mp3
    │   ...
    │   └── 016.mp3
    ├── 03
    │   ├── 001.mp3
    │   ├── 002.mp3
    │   ├── 003.mp3
    │   ...
    │   └── 020.mp3
    └── 04
        ├── 001.mp3
        ├── 002.mp3
        ├── 003.mp3
        ...
        └── 019.mp3

list sdcard content (overview)

    $ tonuino-sdcard -l /Volumes/TonUINO
    /Volumes/TonUINO/01: Artist: Was ist Was, Album: Die Sterne - Die Zeit
    /Volumes/TonUINO/02: Artist: Philipp Schepmann, Album: Der kleine Drache Kokosnuss und die Wetterhexe
    /Volumes/TonUINO/03: Artist: Reinhard Lakomy & Monika Ehrhardt, Album: Der Traumzauberbaum
    /Volumes/TonUINO/04: various artists/albums

list sdcard content (details)

    $ tonuino-sdcard -l /Volumes/TonUINO -v
    /Volumes/TonUINO/01
      001.mp3 => Artist: Was ist Was, Album: Die Sterne - Die Zeit, Title: Die Sterne 01
      002.mp3 => Artist: Was ist Was, Album: Die Sterne - Die Zeit, Title: Die Sterne 02
      003.mp3 => Artist: Was ist Was, Album: Die Sterne - Die Zeit, Title: Die Sterne 03
      ...
      025.mp3 => Artist: Was ist Was, Album: Die Sterne - Die Zeit, Title: Die Zeit 12

    /Volumes/TonUINO/02
      001.mp3 => Artist: Philipp Schepmann, Album: Der kleine Drache Kokosnuss und die Wetterhexe, Title: Der kleine Drache Kokosnuss
      002.mp3 => Artist: Philipp Schepmann, Album: Der kleine Drache Kokosnuss und die Wetterhexe, Title: Die Hagelhose Teil 1
      003.mp3 => Artist: Philipp Schepmann, Album: Der kleine Drache Kokosnuss und die Wetterhexe, Title: Auf geht's auf auf zum Strand
      ...
      016.mp3 => Artist: Philipp Schepmann, Album: Der kleine Drache Kokosnuss und die Wetterhexe, Title: Der kleine Drache Kokosnuss - Reprise

    /Volumes/TonUINO/03
      001.mp3 => Artist: Reinhard Lakomy & Monika Ehrhardt, Album: Der Traumzauberbaum, Title: Traumzauberbaum
      002.mp3 => Artist: Reinhard Lakomy & Monika Ehrhardt, Album: Der Traumzauberbaum, Title: Küsschenlied
      003.mp3 => Artist: Reinhard Lakomy & Monika Ehrhardt, Album: Der Traumzauberbaum, Title: Der Pfannkuchenschreck
      ...
      020.mp3 => Artist: Reinhard Lakomy & Monika Ehrhardt, Album: Der Traumzauberbaum, Title: Traumreise

    /Volumes/TonUINO/04
      001.mp3 => No ID3 tag
      002.mp3 => Artist: Lena Sonnenschein, Felix Froehlich & die Kita-Kids, Album: Die 60 besten traditionellen Kinderlieder (CD3), Title: Hey, Pippi Langstrumpf
      003.mp3 => Artist: Deine Freunde, Album: Kindsköpfe, Title: Schlagzeuglied
      ...
      019.mp3 => Artist: Fun-Kids, Album: Tierisch tolle Kinderhits, Title: Hier kommt die Maus

copy to sdcard and overwrite existing folder

    $ tonuino-sdcard -c Music/WasIstWas/DasAlteÄgyptenUndPyramiden/ /Volumes/TonUINO/02 -r
    $ tonuino-sdcard -l /Volumes/TonUINO
    /Volumes/TonUINO/01: Artist: Was ist Was, Album: Die Sterne - Die Zeit
    /Volumes/TonUINO/02: Artist: Was ist was, Album: Das alte Ägypten + Pyramiden
    /Volumes/TonUINO/03: Artist: Reinhard Lakomy & Monika Ehrhardt, Album: Der Traumzauberbaum
    /Volumes/TonUINO/04: various artists/albums

sdcard housekeeping and reordering

    $ ls /Volumes/TonUINO
    01	02	03	04
    $ rm -rf /Volumes/TonUINO/03
    $ ls /Volumes/TonUINO
    01	02	04
    $ tonuino-sdcard -R /Volumes/TonUINO
    $ ls /Volumes/TonUINO
    01	02	03

adding files to an existing directory on the sdcard

    $ ls -1 /Volumes/TonUINO/03
    001.mp3
    002.mp3
    003.mp3
    ...
    019.mp3
    $ tonuino-sdcard -c Music/tmp /Volumes/TonUINO/03 -a
    $ ls -1 /Volumes/TonUINO/03
    001.mp3
    002.mp3
    003.mp3
    ...
    019.mp3
    020.mp3
    021.mp3

### Roadmap:

* honor cd collections
