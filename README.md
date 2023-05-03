# K-mer Models

K-mer level tables are provided for development use.
These tables may be used with Remora for optimal modified base detection performance.

As opposed to legacy k-mer models, k-mer level tables contain only the expected level for each k-mer.
The expected level table is in standard units (approximately 0 mean and 1 standard deviation spread).

K-mer tables will be stored in directories corresponding to the sequencing condition.

## RNA Models

RNA model k-mers are stored in 5' to 3' direction, matching output basecalls and reference orientation.
Note that current RNA chemistries produce raw signal in the 3' to 5' direction.
Thus k-mers should be reversed when analyzing original sequencing orientation signal/sequence.
