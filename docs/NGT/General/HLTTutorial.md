# Some commands from the HLT Tutorial

Get the HLT configuration from ConfDB:

```bash
hltGetConfiguration /dev/CMSSW_14_2_0/GRun \
   --globaltag 142X_mcRun3_2025_realistic_v7 \
   --mc \
   --unprescale \
   --output minimal \
   --max-events 100 \
   --input /store/mc/Run3Winter25Digi/TT_TuneCP5_13p6TeV_powheg-pythia8/GEN-SIM-RAW/142X_mcRun3_2025_realistic_v7-v2/130000/0174bea8-1bb2-442c-ab23-c0864b50a3a0.root \
   --eras Run3_2025 --l1-emulator uGT --l1 L1Menu_Collisions2024_v1_3_0_xml \
   > hltMC.py

cmsRun hltMC.py >& hltMC.log
```