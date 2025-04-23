# Documenatation for The Optimizer

Follow the instructions in the README of the main repository: [cms-ngt-hlt/cms-reco-optimizer](https://github.com/cms-ngt-hlt/cms-reco-optimizer/tree/PixelPatatrackDev?tab=readme-ov-file#installation)

## Input files

- Single Muon samples

Configuration from the default workflow for "SingleMuPt15Eta0_0p4":
```bash
runTheMatrix.py -w upgrade -l 29690.402 -j 0
```

Configuration from the default workflow for "SingleMuPt15Eta1p7_2p7":
```bash
runTheMatrix.py -w upgrade -l 29689.402 -j 0
```

Run the first two steps:
```bash
cmsRun SingleMuPt15Eta0_0p4_cfi_GEN_SIM.py
cmsRun step2_DIGI_L1TrackTrigger_L1_L1P2GT_DIGI2RAW_HLT.py
```

- TTbar samples

Configuration from the default workflow for "TTbar" without pile-up:
```bash
runTheMatrix.py -w upgrade -l 29634.402 -j 0
```

Run the first two steps:
```bash
cmsRun TTbar_14TeV_TuneCP5_cfi_GEN_SIM.py
cmsRun step2_DIGI_L1TrackTrigger_L1_L1P2GT_DIGI2RAW_HLT_PU.py
```

## Plot of the SimDoublets before optimizing

To plot the doublets before optimizing the cuts, use the analyzer in `src/Validation/TrackingMCTruth/test`".
Change the input file location and run:
```bash
cmsRun simDoubletsPhase2_TEST.py
cmsRun simDoubletsPhase2_HARVESTING.py
```

The plots are saved in `DQM_V0001_R000000001__Global__CMSSW_X_Y_Z__RECO.root`.

Plot with Jan's package:
```bash
cd /data/user/evernazz/PixelPatatrack/2025_03_05/CMSSW_15_0_0_pre3/src/sakura
export PYTHONPATH=${PYTHONPATH}:$PWD/sakura
python3 simplotter/makeCutPlots.py /data/user/evernazz/PixelPatatrack/2025_03_05/CMSSW_15_0_0_pre3/src/Validation/TrackingMCTruth/test/DQM_V0001_R000000001__Global__CMSSW_X_Y_Z__RECO.root /data/user/evernazz/PixelPatatrack/2025_03_05/CMSSW_15_0_0_pre3/src/Validation/TrackingMCTruth/test/simDoubletsPhase2_TEST.py -d TTbar_14Tev -n -1 -a simDoubletsAnalyzerPhase2
```

It is not possible to take the parameters directly from `hltPhase2PixelTracksSoA_cfi.py`