# Big-fish trial 1

Notes.md - notes on what we did tying out big fish

# 2022-10-03

## Pick some data to start with

All Marah's smFISH data from Amsterdam 2022 are in `/Volumes/wallace_rna/bigdata/2022/Marah/`

We decided to test on one wild-type sample:
`220429/yET915rp1-ASH1CLB2Q670-SRL1CFL610-SUN4Q570_06_CY5, CY3.5 NAR, CY3, DAPI.tif`

Opened in Fiji.
Split the stack into 4 with Image > Stack > Tools > Stack Splitter, divided into 4.

Then manually inspected DAPI channel to see the slices containing cells.
Chose stacks 14-33 as best, then did max Z-projection with Image > Stack > Z-project.

ImageJ macro record did:
```
run("Z Project...", "start=14 stop=33 projection=[Max Intensity]");
```

Saved max projection as:
`data/2022-04-29_yET915rp1-ASH1CLB2Q670-SRL1CFL610-SUN4Q570_06_DAPI_MAX.tif`

Checked which the corresponding DIC image was visually (mismatches in image number due to image acquisition procedure), it was `yET915rp1-ASH1CLB2Q670-SRL1CFL610-SUN4Q570_08_DIC-100.tif`.

Also saved DIC image as:
`data/2022-04-29_yET915rp1-ASH1CLB2Q670-SRL1CFL610-SUN4Q570_08_DIC-100.tif`


## Start big-fish


```bash
conda activate bigfish_env

# change directory to big-fish-trial
## EDIT THIS FOR YOUR OWN COMPUTER
cd Repos/big-fish-trial-2022-10

jupyter notebook
```