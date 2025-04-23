12.**HLT_Ele26_WP70_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleTkEle36 or pSingleIsoTkEle28'

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleTkEle36](../Phase2Menu_Legacy/SingleTkEle36.html) : select one EGamma (`CL2Electrons`) with $p_T>36$ GeV - *[Table](../Tables/pSingleTkEle36.md)*
- [pSingleIsoTkEle28](../Phase2Menu_Legacy/SingleIsoTkEle28.html) : select one EGamma (`CL2Electrons`) with $p_T>28$ GeV - *[Table](../Tables/pSingleIsoTkEle28.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltEG26EtL1SeededFilter](../Phase2Menu_Legacy/hltEG26EtL1SeededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>26$ GeV (same threshold in EB and EE)

- [hltEle26WP70ClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70ClusterShapeL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")`

- [hltEle26WP70ClusterShapeSigmavvL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70ClusterShapeSigmavvL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2vv")`

- [hltEle26WP70ClusterShapeSigmawwL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70ClusterShapeSigmawwL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2ww")`

- [hltEle26WP70HgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70HgcalHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")`

- [hltEle26WP70HEL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70HEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEL1Seeded")`

- [hltEle26WP70EcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70EcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoL1Seeded")`

- [hltEle26WP70HgcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70HgcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoL1Seeded")`

- [hltEle26WP70HcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70HcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoL1Seeded")`

- [hltEle26WP70PixelMatchL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70PixelMatchL1SeededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltEle26WP70PMS2L1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70PMS2L1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsL1Seeded","s2")`

- [hltEle26WP70GsfOneOEMinusOneOPL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfOneOEMinusOneOPL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","OneOESuperMinusOneOP")`

- [hltEle26WP70GsfDetaL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfDetaL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","DetaSeed")`

- [hltEle26WP70GsfDphiL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfDphiL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","Dphi")`

- [hltEle26WP70BestGsfNLayerITL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70BestGsfNLayerITL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsL1Seeded","NLayerIT")`

- [hltEle26WP70BestGsfChi2L1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70BestGsfChi2L1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsL1Seeded","Chi2")`

- [hltEle26WP70GsfTrackIsoFromL1TracksL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfTrackIsoFromL1TracksL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleL1TrkIsoL1Seeded")`

- [hltEle26WP70GsfTrackIsoL1SeededFilter](../Phase2Menu_Legacy/hltEle26WP70GsfTrackIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEleGsfTrackIsoL1Seeded")`
