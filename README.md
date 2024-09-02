# extstomp

I often hear people saying that it is not possible to set ctime or btime (aka crtime) on files in Linux. This is incorrect. While the `touch` command only lets you set atime and mtime, you can set all timestamps using `debugfs`.

This script is an easier way of setting whatever timestamps you want. You may set all timestamps to a single value using only one command, or set each timestamp individually using multiple invocations. You can change timestamps on multiple files at the same time.

The script also has a mode that allows you to copy timestamps from an existing file and apply those timestamps to one or more files.

Command syntax is always available with `-h`:

```
Usage: extstomp [-COvh] [-e nanosec | -E extra] -[macb] [-T time | -S sourcefile] file ...

    Optional modifiers:
    -C    Do not drop caches when program ends (changes may not be visible)
    -O    File system is "old": EXT3 or earlier (no fractional seconds)
    -v    Be verbose and show all file timestamps after changes made
    -h    Show this message and exit

    Specify fractional seconds field (if not specified, random value will be used):
    -e nanosec    Specify nanosecond value (will be bit shifted)
    -E extra      Specify exact field including extra bits (will not be bit shifted)

    Time fields to set (must choose at least one, may choose multiple):
    -m    Set mtime (file content last modified)
    -a    Set atime (file last access time)
    -c    Set ctime (metadata change time)
    -b    Set crtime (file creation time)

    Specify time to set (must choose only one option):
    -T time          Argument may be any format recognized by system "date" program.
                     Time value cannot be earlier than 1901-12-13 20:45:52 UTC or later
                     than 2446-05-10 22:38:55 UTC.

    -S sourcefile    Specify file path. Timestamps will be copied from source file exactly.
                     -e, -E options will be ignored.
```
