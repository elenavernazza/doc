# Running The Optimizer

Follow the instructions in the README of the main repository: [cms-ngt-hlt/cms-reco-optimizer](https://github.com/cms-ngt-hlt/cms-reco-optimizer/tree/PixelPatatrackDev?tab=readme-ov-file#run-the-optimizer)

## Current developments

- Include the new SimpleBinnedValidation.cc module to compute the metrics binned in eta and pt: [link](https://github.com/cms-sw/cmssw/commit/8e9e3828f4cd84d717a288ef610d2c2c0818f1fb)
- Expose all parameters, based on Luca's developments: [link](https://github.com/cms-sw/cmssw/commit/eeea34447fc55f02af617cafec7ace6d6c9609ed)
- Optimization on ttbar 10k events with only scalars:
```bash
cd /data/user/evernazz/PixelPatatrack/2025_03_05/CMSSW_15_0_0_pre3/src/cms-reco-optimizer
export PYTHONPATH=${PYTHONPATH}:$PWD/The-Optimizer
/optimize_reco.py hlt_pixel_optimization.py -t hltPhase2PixelTracksSoA -v hltPhase2PixelTracks \
-f file:/data/user/evernazz/PixelPatatrack/2025_01_27/CMSSW_15_0_0_pre2/src/29634.402_TTbar_14TeV+Run4D110_Patatrack_PixelOnlyAlpaka/step2.root --num_events -1 \
--num_threads 32 -a 32 -i 10 \
-b examples/config.json -p cellZ0Cut,cellPtCut,cellMinYSizeB1,cellMinYSizeB2,cellMaxDYSize12,cellMaxDYSize,cellMaxDYPred \
-o TTBar_SplitBinnedMetrics_AllScalarCuts
```
- Plot simDoublets and cuts using repo by Jan [link](https://github.com/JanGerritSchulz/sakura/tree/master)
- Script to get the optimizer output and save it to `hltPhase2PixelTracksSoA_cfi.py`
- Remote TP selector from eta binned metrics (on openlab machines):

```bash
python3 -m venv opt_env
pip3 activate opt_env
source opt_env/bin/activate
pip3 install "numpy<2"
```

```bash
cd /data/evernazz/2025_03_05/CMSSW_15_0_0_pre3/src/cms-reco-optimizer
export PYTHONPATH=${PYTHONPATH}:$PWD/The-Optimizer
./optimize_reco.py hlt_pixel_optimization.py -t hltPhase2PixelTracksSoA -v hltPhase2PixelTracks \
-f file:/data/evernazz/2025_03_05/CMSSW_15_0_0_pre3/src/29634.402_TTbar_14TeV+Run4D110_Patatrack_PixelOnlyAlpaka/step2.root --num_events -1 \
--num_threads 64 -a 32 -i 10 \
-b examples/config.json -p cellZ0Cut,cellPtCut,cellMinYSizeB1,cellMinYSizeB2,cellMaxDYSize12,cellMaxDYSize,cellMaxDYPred \
-o TTBar_SplitBinnedMetricsNoTPselector_AllScalarCuts
```

## Plans

- Add option to obtain min and max in each distribution, in order to define the parameter regions where to scan (save the numbers in the `examples/config.json` that will be used to run the optimization)
- On the openlab machines, I have tested Jan's option: 
`process.g4SimHits.TrackerSD.EnergyThresholdForPersistencyInGeV = cms.double(0.)`

- Optimization on ttbar 10k events with all cuts (scalars and vectors)
```bash
cd /data/user/evernazz/PixelPatatrack/2025_03_05/CMSSW_15_0_0_pre3/src/cms-reco-optimizer
export PYTHONPATH=${PYTHONPATH}:$PWD/The-Optimizer
/optimize_reco.py hlt_pixel_optimization.py -t hltPhase2PixelTracksSoA -v hltPhase2PixelTracks \
-f file:/data/user/evernazz/PixelPatatrack/2025_01_27/CMSSW_15_0_0_pre2/src/29634.402_TTbar_14TeV+Run4D110_Patatrack_PixelOnlyAlpaka/step2.root --num_events -1 \
--num_threads 32 -a 32 -i 10 \
-b examples/config.json -p cellZ0Cut,cellPtCut,cellMinYSizeB1,cellMinYSizeB2,cellMaxDYSize12,cellMaxDYSize,cellMaxDYPred,phiCuts,cellMinz,cellMaxz,cellMaxr \
-o test
```

- Script to get the optimizer output and save it to `hltPhase2PixelTracksSoA_cfi.py`
- Script to get the optimizer output and save it to `simDoubletsPhase2_TEST.py`

- Plots showing the efficiency and fake before and after the optimization
- Plots showing the cuts on SimDoublets before and after the optimization


```bash
cmsRun optimize.hlt_pixel_optimization_20250305.151533_TTBar_SplitBinnedMetrics_AllScalarCuts/process_to_run.py parametersFile=optimize.hlt_pixel_optimization_20250305.151533_TTBar_SplitBinnedMetrics_AllScalarCuts/checkpoint/checkpoint/Configuration/new_point78.csv outputFile=optimize.hlt_pixel_optimization_20250305.151533_TTBar_SplitBinnedMetrics_AllScalarCuts/checkpoint/checkpoint/Configuration/new_point78.root
```