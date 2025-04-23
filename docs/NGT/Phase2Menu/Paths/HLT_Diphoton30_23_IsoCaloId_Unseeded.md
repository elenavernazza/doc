3.**HLT_Diphoton30_23_IsoCaloId_Unseeded**

<span style="color:orange">**L1 seed**</span>: `pDoubleEGEle37_24 or pDoubleIsoTkPho22_12`

- [pDoubleEGEle37_24](../Phase2Menu_Legacy/DoubleEGEle3724.html) : select two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively - *[Table](../Tables/pDoubleEGEle37_24.md)*
- [pDoubleIsoTkPho22_12](../Phase2Menu_Legacy/DoubleIsoTkPho2212.html) : select two EGamma (`CL2Photons`) with tracker isolation requirement (?) with $p_T>22$ and $p_T>12$ GeV, respectively - *[Table](../Tables/pDoubleIsoTkPho22_12.md)*

    * <span style="color:red">**NOTE**</span>: Why are the paths called differently ("EGEle" vs "IsoTkPho") if they are consuming the same collection, only changing the pT threshold and minDR? What is minDR and where is it used? It never appears in the class `L1GTDoubleObjectCond` [here](https://github.com/cms-sw/cmssw/blob/master/L1Trigger/Phase2L1GT/plugins/L1GTDoubleObjectCond.cc).

<span style="color:green">**HLT filters**</span>:

When the reconstruction of photons and electrons is "Unseeded", the clustering is performed everywhere (timing is largely affected).

- [hltEgammaCandidatesWrapperUnseeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html):<br> 
select `hltEgammaCandidatesUnseeded` with isolation condition

- [hltEG30EtUnseededFilter](../Phase2Menu_Legacy/hltEG30EtUnseededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>30$ GeV (same threshold in EB and EE)

- [hltDiEG23EtUnseededFilter](../Phase2Menu_Legacy/hltDiEG23EtUnseededFilter.html):<br> 
select two (`ncandcut=2`) `hltEgammaCandidatesUnseeded` objects with $p_T>23$ GeV (same threshold in EB and EE)

- [hltDiEG3023IsoCaloIdClusterShapeUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdClusterShapeUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeUnseeded","sigmaIEtaIEta5x5")`

- [hltDiEG3023IsoCaloIdClusterShapeSigmavvUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdClusterShapeSigmavvUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","sigma2vv")`

- [hltDiEG3023IsoCaloIdClusterShapeSigmawwUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdClusterShapeSigmawwUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","sigma2ww")`

- [hltDiEG3023IsoCaloIdHgcalHEUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHgcalHEUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","hForHOverE")`

- [hltDiEG3023IsoCaloIdHEUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHEUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEUnseeded")`

- [hltDiEG3023IsoCaloIdEcalIsoUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdEcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoUnseeded")`

- [hltDiEG3023IsoCaloIdHgcalIsoUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHgcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoUnseeded")`

- [hltDiEG3023IsoCaloIdHcalIsoUnseededFilter](../Phase2Menu_Legacy/hltDiEG3023IsoCaloIdHcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoUnseeded")`
