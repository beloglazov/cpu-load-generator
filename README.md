# cpu-load-generator – a tool for generating a set of subsequent CPU utilization levels

This tools takes a file as an argument, which lists a set of CPU utilization levels as numbers in
the [0.0, 1.0] range. The numbers in the file are separated by new lines. The tool also accepts a
parameter specifying the required time interval between two subsequent CPU utilization levels. Then,
cpu-load-generator goes through the sequence of the CPU utilization levels and generates each CPU
utilization level for the specified time interval.

Internally, to create each CPU utilization level cpu-load-generator calls the lookbusy synthetic
load generator developed by Devin Carraway, released under the GPL license, and available from
http://www.devin.com/lookbusy/


## License

The tool is released under the Apache 2.0 license

Copyright (C) 2012 Anton Beloglazov
