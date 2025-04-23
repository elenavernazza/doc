11.**HLT_Ele115_NonIso_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleTkEle36`

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleTkEle36](../Phase2Menu_Legacy/SingleTkEle36.html) : select one EGamma (`CL2Electrons`) with $p_T>36$ GeV - *[Table](../Tables/pSingleTkEle36.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltEG115EtL1SeededFilter](../Phase2Menu_Legacy/hltEG115EtL1SeededFilter.html):<br>
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>115$ GeV (same threshold in EB and EE)

- [hltEle115NonIsoClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoClusterShapeL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")`

- [hltEle115NonIsoClusterShapeSigmavvL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoClusterShapeSigmavvL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2vv")`

- [hltEle115NonIsoClusterShapeSigmawwL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoClusterShapeSigmawwL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2ww")`

- [hltEle115NonIsoHgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoHgcalHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")`

- [hltEle115NonIsoHEL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEL1Seeded")`

- [hltEle115NonIsoPixelMatchL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoPixelMatchL1SeededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltEle115NonIsoPMS2L1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoPMS2L1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsL1Seeded","s2")`

- [hltEle115NonIsoGsfDetaL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoGsfDetaL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","DetaSeed")`

- [hltEle115NonIsoGsfDphiL1SeededFilter](../Phase2Menu_Legacy/hltEle115NonIsoGsfDphiL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","Dphi")`
