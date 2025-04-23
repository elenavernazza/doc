13.**HLT_Ele26_WP70_Unseeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleTkEle36 or pSingleIsoTkEle28'

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleTkEle36](../Phase2Menu_Legacy/SingleTkEle36.html) : select one EGamma (`CL2Electrons`) with $p_T>36$ GeV - *[Table](../Tables/pSingleTkEle36.md)*
- [pSingleIsoTkEle28](../Phase2Menu_Legacy/SingleIsoTkEle28.html) : select one EGamma (`CL2Electrons`) with $p_T>28$ GeV - *[Table](../Tables/pSingleIsoTkEle28.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperUnseeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html):<br> 
select `hltEgammaCandidatesUnseeded` with isolation condition

- [hltEG26EtUnseededFilter](../Phase2Menu_Legacy/hltEG26EtUnseededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>26$ GeV (same threshold in EB and EE)

- [hltEle26WP70ClusterShapeUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70ClusterShapeUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeUnseeded","sigmaIEtaIEta5x5")`

- [hltEle26WP70ClusterShapeSigmavvUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70ClusterShapeSigmavvUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","sigma2vv")`

- [hltEle26WP70ClusterShapeSigmawwUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70ClusterShapeSigmawwUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","sigma2ww")`

- [hltEle26WP70HgcalHEUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70HgcalHEUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","hForHOverE")`

- [hltEle26WP70HEUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70HEUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEUnseeded")`

- [hltEle26WP70EcalIsoUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70EcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoUnseeded")`

- [hltEle26WP70HgcalIsoUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70HgcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoUnseeded")`

- [hltEle26WP70HcalIsoUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70HcalIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoUnseeded")`

- [hltEle26WP70PixelMatchUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70PixelMatchUnseededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltEle26WP70PMS2UnseededFilter](../Phase2Menu_Legacy/hltEle26WP70PMS2UnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsUnseeded","s2")`

- [hltEle26WP70GsfOneOEMinusOneOPUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfOneOEMinusOneOPUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsUnseeded","OneOESuperMinusOneOP")`

- [hltEle26WP70GsfDetaUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfDetaUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsUnseeded","DetaSeed")`

- [hltEle26WP70GsfDphiUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfDphiUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsUnseeded","Dphi")`

- [hltEle26WP70BestGsfNLayerITUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70BestGsfNLayerITUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsUnseeded","NLayerIT")`

- [hltEle26WP70BestGsfChi2UnseededFilter](../Phase2Menu_Legacy/hltEle26WP70BestGsfChi2UnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsUnseeded","Chi2")`

- [hltEle26WP70GsfTrackIsoFromL1TracksUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfTrackIsoFromL1TracksUnseededFilter.html):<br>
`varTag = cms.InputTag("hltEgammaEleL1TrkIsoUnseeded")`

- [hltEle26WP70GsfTrackIsoUnseededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfTrackIsoUnseededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleGsfTrackIsoUnseeded")`
