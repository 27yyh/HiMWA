# HiMWA
A Hierarchical Multiple-Wave Admixture Model for Inferring Complex Admixture Histories

Please ensure `HiMWA.py` is in the same directory as the [`src/`](src/) folder.

## Input Files 
The format of input ancestral tracts file is same as HierarchyMix. Each row represents an ancestral tract characterized by the following parameters: (1) the genetic distance of start-point (in Morgans), (2) the genetic distance of end-point (in Morgans), (3) the ancestry of origin, (4) the index of admixed haplotype, and (5) the chromosome label. All genetic positions are specified in Morgans (M) with decimal precision. An example segmentation file `example.seg` is provided in the [`examples/`](examples/) directory.  

## Output Files 
The format of output model file is same as MultiWaver series and HierarchyMix software. The example generates an output file `example.txt`.

To run with this sample data:

```bash
python HiMWA.py --input examples/example.seg --output examples/example
```

## Arguments and Options 
--input	string	Input file name	required
--output	string	Prefix of output file	optional, default = ‘out’
--lower	float	Lower bound to discard short tracts	optional, default = 0
--lowerEF	float	Lower bound to discard short tracts of admixed ancestral population	optional, default = 0
--bootstrap	int	Number of bootstrapping	optional, default = 0
--ci	string	Confidence level of bootstrapping confidence interval	optional, default = 0.95
-h	/	Print help message	/

## Notes 
It should be noted that the model selection of HiMWA may be unreliable for admixed populations with extremely biasd admixture proportions. Furthermore, in scenarios with multiple recent admixture waves, the inferred times of recent admixture events by HiMWA may be overestimated. It is advised to correct the overestimation of the admixture times referring the strategy in this study under specific model configurations.
