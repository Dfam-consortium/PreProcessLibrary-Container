TODO: <br>
use Git credentials to remove 2nd login on build
https://git-scm.com/docs/gitcredentials
## Requirements
- Singularity install
- GitHub credentials

## Building
Build as an interactive directory:
```
sudo singularity build --sandbox PreProcessLibrary/ PreProcessLibrary.def
```
Build as an image (SIF) file:
```
sudo singularity build PreProcessLibrary.sif PreProcessLibrary.def
```
Copy directory into image file:
```
sudo singularity build PreProcessLibrary.sif PreProcessLibrary/
```

## Use
Generate `library-info.json`:
```
singularity run --app setup PreProcessLibrary.sif
```

Run EBI Pipeline:
```
singularity run --app ebi PreProcessLibrary.sif <accession#> <accession#.families.stk.gz>
```

Run Individual Steps:
```
singularity run PreProcessLibrary.sif 10
singularity run PreProcessLibrary.sif 40 45
```