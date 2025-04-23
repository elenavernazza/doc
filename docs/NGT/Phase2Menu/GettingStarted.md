# Documentation for the Phase 2 HLT Menu

** The up-to-date documentation hase been published in the [HLT Upgrade Documentation](https://cmshltupgrade.docs.cern.ch/Phase2Menu/ListOfPaths/) **

### My instructions

Produce the html webpage for the Phase 2 menu:
```bash
cmsrel CMSSW_15_0_0_pre3
cd CMSSW_15_0_0_pre3/src
cmsenv
git cms-init
git cms-addpkg HLTrigger/Configuration
cd HLTrigger/Configuration/python/HLT_75e33/test/
```

[In my case, I hado to cherry-pick the [PR 47379](https://github.com/cms-sw/cmssw/pull/47379) to correct for redundant L1 paths, but these changes will be available starting from release `15_1_X`.]

Inside the file `runHLTTiming.sh` you can find a `cmsDriver.py` command that is continuously run to evaluate the performance (it is possible to monitor its performance in [this webpage](https://cmssdt.cern.ch/SDT/html/cmssdt-ib/#/ib/CMSSW_15_1_X) under "HLT Phase2 Timing"). Use this command, removing the timing option, and produce a step2 configuration which includes the Phase 2 menu.
```bash
cmsDriver.py Phase2 -s L1P2GT,HLT:75e33 --processName=HLTX \
  --conditions auto:phase2_realistic_T33 --geometry ExtendedRun4D110 \
  --era Phase2C17I13M9 \
  --customise SLHCUpgradeSimulations/Configuration/aging.customise_aging_1000 \
  --eventcontent FEVTDEBUGHLT \
  --filein=file:step1.root \
  --mc --nThreads 4 --inputCommands='keep *, drop *_hlt*_*_HLT, drop triggerTriggerFilterObjectWithRefs_l1t*_*_HLT' \
  -n 1000 --no_exec --output={}
```

Same with Alpaka modifier:
```bash
cmsDriver.py Phase2_Alpaka -s L1P2GT,HLT:75e33 --processName=HLTX \
  --procModifiers alpaka \
  --conditions auto:phase2_realistic_T33 --geometry ExtendedRun4D110 \
  --era Phase2C17I13M9 \
  --customise SLHCUpgradeSimulations/Configuration/aging.customise_aging_1000 \
  --eventcontent FEVTDEBUGHLT \
  --filein=file:step1.root \
  --mc --nThreads 4 --inputCommands='keep *, drop *_hlt*_*_HLT, drop triggerTriggerFilterObjectWithRefs_l1t*_*_HLT' \
  -n 1000 --no_exec --output={}
```

Same with TICLv5 modifier:
```bash
cmsDriver.py Phase2_TICLv5 -s L1P2GT,HLT:75e33 --processName=HLTX \
  --procModifiers ticl_v5 \
  --conditions auto:phase2_realistic_T33 --geometry ExtendedRun4D110 \
  --era Phase2C17I13M9 \
  --customise SLHCUpgradeSimulations/Configuration/aging.customise_aging_1000 \
  --eventcontent FEVTDEBUGHLT \
  --filein=file:step1.root \
  --mc --nThreads 4 --inputCommands='keep *, drop *_hlt*_*_HLT, drop triggerTriggerFilterObjectWithRefs_l1t*_*_HLT' \
  -n 1000 --no_exec --output={}
```

Get this python script ([Download py2html_refactor.py](py2html_refactor.py)) and produce the html folder by running:
```bash
python3 py2html_refactor.py -i Phase2_L1P2GT_HLT.py -o html_legacy
python3 py2html_refactor.py -i Phase2_Alpaka_L1P2GT_HLT.py -o html_alpaka
python3 py2html_refactor.py -i Phase2_TICLv5_L1P2GT_HLT.py -o html_ticlv5
```

The output is a html folder, with links to the full menu.