2.**HLT_Diphoton30_23_IsoCaloId_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pDoubleEGEle37_24 or pDoubleIsoTkPho22_12`

- [pDoubleEGEle37_24](../Phase2Menu_Legacy/DoubleEGEle3724.html) : select two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively - *[Table](../Tables/pDoubleEGEle37_24.md)*
- [pDoubleIsoTkPho22_12](../Phase2Menu_Legacy/DoubleIsoTkPho2212.html) : select two EGamma (`CL2Photons`) with tracker isolation requirement (?) with $p_T>22$ and $p_T>12$ GeV, respectively - *[Table](../Tables/pDoubleIsoTkPho22_12.md)*

    * <span style="color:red">**NOTE**</span>: Why are the paths called differently ("EGEle" vs "IsoTkPho") if they are consuming the same collection, only changing the pT threshold and minDR? What is minDR and where is it used? It never appears in the class `L1GTDoubleObjectCond` [here](https://github.com/cms-sw/cmssw/blob/master/L1Trigger/Phase2L1GT/plugins/L1GTDoubleObjectCond.cc).

<span style="color:green">**HLT filters**</span>:

When the reconstruction of photons and electrons is "L1 seeded", the clustering is only performed in a $\Delta R = 0.35$ cone from the L1 EGamma objects in [this module](../Phase2Menu_Legacy/hltEcalBarrelDigisInRegions.html).

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

    * <span style="color:red">**NOTE**</span>: What is this module actually doing? 

- [hltEG30EtL1SeededFilter](../Phase2Menu_Legacy/hltEG30EtL1SeededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>30$ GeV (same threshold in EB and EE)

- [hltDiEG23EtL1SeededFilter](../Phase2Menu_Legacy/hltDiEG23EtL1SeededFilter.html):<br> 
select two (`ncandcut=2`) `hltEgammaCandidatesL1Seeded` objects with $p_T>23$ GeV (same threshold in EB and EE)

- [hltDiEG3023IsoCaloIdClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdClusterShapeL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")`

- [hltDiEG3023IsoCaloIdClusterShapeSigmavvL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdClusterShapeSigmavvL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2vv")`

- [hltDiEG3023IsoCaloIdClusterShapeSigmawwL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdClusterShapeSigmawwL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2ww")`

- [hltDiEG3023IsoCaloIdHgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHgcalHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")`

- [hltDiEG3023IsoCaloIdHEL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEL1Seeded")`

- [hltDiEG3023IsoCaloIdEcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdEcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoL1Seeded")`

- [hltDiEG3023IsoCaloIdHgcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHgcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoL1Seeded")`

- [hltDiEG3023IsoCaloIdHcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoL1Seeded")`
