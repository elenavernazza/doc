15.**HLT_Ele32_WPTight_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleTkEle36 or pSingleIsoTkEle28'

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleTkEle36](../Phase2Menu_Legacy/SingleTkEle36.html) : select one EGamma (`CL2Electrons`) with $p_T>36$ GeV - *[Table](../Tables/pSingleTkEle36.md)*
- [pSingleIsoTkEle28](../Phase2Menu_Legacy/SingleIsoTkEle28.html) : select one EGamma (`CL2Electrons`) with $p_T>28$ GeV - *[Table](../Tables/pSingleIsoTkEle28.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltEG32EtL1SeededFilter](../Phase2Menu_Legacy/hltEG32EtL1SeededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>32$ GeV (same threshold in EB and EE)

- [hltEle32WPTightClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightClusterShapeL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")`

- [hltEle32WPTightClusterShapeSigmavvL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightClusterShapeSigmavvL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2vv")`

- [hltEle32WPTightClusterShapeSigmawwL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightClusterShapeSigmawwL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2ww")`

- [hltEle32WPTightHgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightHgcalHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")`

- [hltEle32WPTightHEL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEL1Seeded")`

- [hltEle32WPTightEcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightEcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoL1Seeded")`

- [hltEle32WPTightHgcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightHgcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoL1Seeded")`

- [hltEle32WPTightHcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightHcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoL1Seeded")`

- [hltEle32WPTightPixelMatchL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightPixelMatchL1SeededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltEle32WPTightPMS2L1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightPMS2L1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsL1Seeded","s2")`

- [hltEle32WPTightGsfOneOEMinusOneOPL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfOneOEMinusOneOPL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","OneOESuperMinusOneOP")`

- [hltEle32WPTightGsfDetaL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfDetaL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","DetaSeed")`

- [hltEle32WPTightGsfDphiL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfDphiL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","Dphi")`

- [hltEle32WPTightBestGsfNLayerITL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightBestGsfNLayerITL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsL1Seeded","NLayerIT")`

- [hltEle32WPTightBestGsfChi2L1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightBestGsfChi2L1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsL1Seeded","Chi2")`

- [hltEle32WPTightGsfTrackIsoFromL1TracksL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfTrackIsoFromL1TracksL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleL1TrkIsoL1Seeded")`

- [hltEle32WPTightGsfTrackIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfTrackIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleGsfTrackIsoL1Seeded")`
