16.**HLT_Ele32_WPTight_Unseeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleTkEle36 or pSingleIsoTkEle28'

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleTkEle36](../Phase2Menu_Legacy/SingleTkEle36.html) : select one EGamma (`CL2Electrons`) with $p_T>36$ GeV - *[Table](../Tables/pSingleTkEle36.md)*
- [pSingleIsoTkEle28](../Phase2Menu_Legacy/SingleIsoTkEle28.html) : select one EGamma (`CL2Electrons`) with $p_T>28$ GeV - *[Table](../Tables/pSingleIsoTkEle28.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperUnseeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html):<br> 
select `hltEgammaCandidatesUnseeded` with isolation condition

- [hltEG32EtUnseededFilter](../Phase2Menu_Legacy/hltEG32EtUnseededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>32$ GeV (same threshold in EB and EE)

- [hltEle32WPTightClusterShapeUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightClusterShapeUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeUnseeded","sigmaIEtaIEta5x5")`

- [hltEle32WPTightClusterShapeSigmavvUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightClusterShapeSigmavvUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","sigma2vv")`

- [hltEle32WPTightClusterShapeSigmawwUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightClusterShapeSigmawwUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","sigma2ww")`

- [hltEle32WPTightHgcalHEUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightHgcalHEUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","hForHOverE")`

- [hltEle32WPTightHEUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightHEUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEUnseeded")`

- [hltEle32WPTightEcalIsoUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightEcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoUnseeded")`

- [hltEle32WPTightHgcalIsoUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightHgcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoUnseeded")`

- [hltEle32WPTightHcalIsoUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightHcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoUnseeded")`

- [hltEle32WPTightPixelMatchUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightPixelMatchUnseededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltEle32WPTightPMS2UnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightPMS2UnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsUnseeded","s2")`

- [hltEle32WPTightGsfOneOEMinusOneOPUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfOneOEMinusOneOPUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsUnseeded","OneOESuperMinusOneOP")`

- [hltEle32WPTightGsfDetaUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfDetaUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsUnseeded","DetaSeed")`

- [hltEle32WPTightGsfDphiUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfDphiUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsUnseeded","Dphi")`

- [hltEle32WPTightBestGsfNLayerITUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightBestGsfNLayerITUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsUnseeded","NLayerIT")`

- [hltEle32WPTightBestGsfChi2UnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightBestGsfChi2UnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsUnseeded","Chi2")`

- [hltEle32WPTightGsfTrackIsoFromL1TracksUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfTrackIsoFromL1TracksUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleL1TrkIsoUnseeded")`

- [hltEle32WPTightGsfTrackIsoUnseededFilter](../Phase2Menu_Legacy/hltEle32WPTightGsfTrackIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleGsfTrackIsoUnseeded")`
