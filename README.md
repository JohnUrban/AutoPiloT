![logo](/img/logo.png)

# AutoPiloT
AutoPiloT : Automated Pilon Tool. Index, map, filter, polish. Repeat.


# Detailed Usage


	AutoPiloT : Automated Pilon Tool.

	Usage: 
		AutoPiloT -i asm.fofn -1 R1 -2 R2 [options t:r:m:Q:q:f:F:J:ST:M:v]


	Quick Start:
		AutoPiloT -i asm.fofn -1 R1 -2 R2


        Running on SLURM:
                 $( basename ${0} ) -i asm.fofn -1 R1 -2 R2 -S


        Resume a job that didn't finish (e.g. that was killed by SLURM) by simply re-running the command again.
                $( basename ${0} ) -i asm.fofn -1 R1 -2 R2 [-S]


        Options:

        -i      FOFN	: Required.
        -1      R1	: Required.
	-2	R2	: Required.
	-t	THREADS	: Default = 2.
	-r	ROUNDS	: Default = 3.
	-m	MAXFRAG	: Default = 600.
	-Q	MINMAPQ	: Default = 20.
	-q	MINBQ	: Default = 20.
	-f	FLANK	: Default = 10.
	-F	MAPFXN	: Default = bowtie2_PE_endtoend_veryfast_concordant_frags_mapqfilt .
			Available Values are:
			+ bowtie2_PE_endtoend_veryfast_concordant_frags_mapqfilt (default)
			# bowtie2_PE_endtoend_veryfast_concordant_frags_mapqfilt,
			# bowtie2_PE_endtoend_ultra_sensitive_concordant_frags_mapqfilt
			# bowtie2_PE_local_veryfast_concordant_frags_mapqfilt
			# bowtie2_PE_local_verysensitive_concordant_frags_mapqfilt
			# bwa_mem_standard_concordant_frags_mapqfilt
	-J	PILONKX	: Default = 8G.
	-S	SLURM	: Use to launch SLURM batch scripts (one per assembly in FOFN) instead of processing serially in current env. Default = false.
	-T	TIME	: Time limit for SLURM. Default = 24:00:00 .
	-M	MEM	: Mem limit for SLURM. Default = 30G .
	-v	VERBOSE	: Default = false.
