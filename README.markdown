galaxy-tools
============

FLS tools and tool-wrappers for Galaxy.

Tools are organised into subdirectories; to add these to your local
Galaxy:

1. Either:
   Copy the subdirectory into your .../galaxy-dist/tools/ directory
   or:
   Make a soft link in .../galaxy-dist/tools/ to the tool subdirectory
   
2. Add an entry for the tool in .../galaxy-dist/tool_conf.xml

You will also need to restart Galaxy for the changes to take effect.

Note:

 * The XML files also contain test for each tool, but the test data is not
   currently in this repository.

 * The tool ids of the FLS tools are weakly namespaced by an "fls_" prefix
   on the tool ids.

fastq_screen
------------
XML and wrapper script for fastq_screen program. Assumes that
fastq_screen program is on the Galaxy user's path, and that
fastq_screen.conf has been configured appropriately for the local
setup.

To add to Galaxy put this somewhere in tool_conf.xml:

    <tool file="fls_fastq_screen/fastq_screen.xml" />

You also need to make a copy of the `fastq_screen.loc` file (sample
version is provided here) which points to one or more fastq_screen `.conf`
files. The user can choose which conf file to use at run time.

`fastq_screen` can be obtained from [http://www.bioinformatics.bbsrc.ac.uk/projects/fastq_screen/]().

qc_boxplotter
-------------
XML and wrapper script for the FLS SOLiD QC boxplotter. Assumes that
`qc_boxplotter.sh` (the driver for the boxplotter) is on the Galaxy
user's path (currently it's in `genomics/NGS-general/`).

To add to Galaxy put this somewhere in tool_conf.xml:

    <tool file="fls_qc_boxplotter/qc_boxplotter.xml" />

SamStats
--------
XML and wrapper script for the FLS SamStats utility. Assumes that the
SamStats.jar file is in .../galaxy-dist/tools-data/shared/jars (a
symbolic link is sufficient).

To add to Galaxy put this somewhere in tool_conf.xml:

    <tool file="fls_samstats/samstats.xml" />