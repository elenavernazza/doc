5.**HLT_DoubleEle25_CaloIdL_PMS2_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pDoubleEGEle37_24 or pDoubleTkEle25_12`

- [pDoubleEGEle37_24](../Phase2Menu_Legacy/DoubleEGEle3724.html) : select two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively - *[Table](../Tables/pDoubleEGEle37_24.md)*
- [pDoubleTkEle25_12](../Phase2Menu_Legacy/DoubleTkEle2512.html) : select two EGamma (`CL2Electrons`) with $p_T>25$ and $p_T>12$ GeV, respectively - *[Table](../Tables/pDoubleTkEle25_12.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltDiEG25EtL1SeededFilter](../Phase2Menu_Legacy/hltDiEG25EtL1SeededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>25$ GeV (same threshold in EB and EE)

- [hltDiEG25CaloIdLClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltDiEG25CaloIdLClusterShapeL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")`

- [hltDiEG25CaloIdLClusterShapeSigmavvL1SeededFilter](../Phase2Menu_Legacy/hltDiEG25CaloIdLClusterShapeSigmavvL1SeededFilter.html): 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2vv")`

- [hltDiEG25CaloIdLHgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltDiEG25CaloIdLHgcalHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")`

- [hltDiEG25CaloIdLHEL1SeededFilter](../Phase2Menu_Legacy/hltDiEG25CaloIdLHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEL1Seeded")`

- [hltDiEle25CaloIdLPixelMatchL1SeededFilter](../Phase2Menu_Legacy/hltDiEle25CaloIdLPixelMatchL1SeededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltDiEle25CaloIdLPMS2L1SeededFilter](../Phase2Menu_Legacy/hltDiEle25CaloIdLPMS2L1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsL1Seeded","s2")`
