# extstomp

I often hear people saying that it is not possible to set ctime or btime (aka crtime) on files in Linux. This is incorrect. While the `touch` command only lets you set atime and mtime, you can set all timestamps using `debugfs`.

This script is an easier way of setting whatever timestamps you want. You may set all timestamps to a single value using only one command, or set each timestamp individually using multiple invocations. You can change timestamps on multiple files at the same time.

The script also has a mode that allows you to copy timestamps from an existing file and apply those timestamps to one or more files.

For a complete list of options, use the `-h` flag.
