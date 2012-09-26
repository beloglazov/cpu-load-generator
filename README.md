# cpu-load-generator – a tool for generating a set of subsequent CPU utilization levels

This tools takes a file as an argument, which lists a set of CPU utilization levels as floating
point numbers in the [0, 1] range. The numbers in the file should be separated by new lines. The
tool accepts another parameter specifying the required time interval between two subsequent CPU
utilization levels. Then, cpu-load-generator goes through the sequence of the CPU utilization levels
and generates each CPU utilization level for the specified time interval. The tool also accepts an
optional parameter that sets the number of CPU cores to utilizes, which defaults to 1.

Internally, to create each CPU utilization level cpu-load-generator calls the `lookbusy` synthetic
load generator developed by Devin Carraway, released under the GPL license, and available from
http://www.devin.com/lookbusy/


## Installation

To use the tool, it is necessary to install the `lookbusy` program first. This can be done using the
included `install-lookbusy.sh` script as follows (the installation requires the sudo password):

```Shell
./install-lookbusy.sh
```


## Usage

>Usage: python cpu-load-generator.py [options] INTERVAL SOURCE
>
>  Generates a set of subsequent CPU utilization levels read from a file.
>  Copyright (C) 2012 Anton Beloglazov. Released under Apache 2.0 license.
>
>  Options:
>    -h, --help          show this help message and exit
>    -n NCPUS, --ncpus=NCPUS
>                        number of CPU cores to utilize [default: 1]
>
>Positional Arguments:
>  INTERVAL  interval between subsequent CPU utilization levels in seconds
>  SOURCE    source file containing a new line separated list of CPU
>              utilization levels specified as floats in the [0, 1] range


## Examples

To generate a sequence of 20%, 90%, and 50% CPU utilization for 20 seconds each on 2 cores using the
`test.data` file, please run:

```Shell
python cpu-load-generator.py -n 2 20 test.data
```

## License

The tool is released under the Apache 2.0 license

Copyright (C) 2012 Anton Beloglazov
