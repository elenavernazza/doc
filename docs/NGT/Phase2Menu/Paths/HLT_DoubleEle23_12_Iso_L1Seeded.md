4.**HLT_DoubleEle23_12_Iso_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pDoubleEGEle37_24 or pDoubleTkEle25_12 or pIsoTkEleEGEle22_12`

- [pDoubleEGEle37_24](../Phase2Menu_Legacy/DoubleEGEle3724.html) : select two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively - *[Table](../Tables/pDoubleEGEle37_24.md)*
- [pDoubleTkEle25_12](../Phase2Menu_Legacy/DoubleTkEle2512.html) : select two EGamma (`CL2Electrons`) with $p_T>25$ and $p_T>12$ GeV, respectively - *[Table](../Tables/pDoubleTkEle25_12.md)*
- [pIsoTkEleEGEle22_12](../Phase2Menu_Legacy/IsoTkEleEGEle2212.html) : select one EGamma (`CL2Electrons`) with $p_T>22$ GeV and one EGamma (`CL2Photons`) with $p_T>12$ GeV - *[Table](../Tables/pIsoTkEleEGEle22_12.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltEG23EtL1SeededFilter](../Phase2Menu_Legacy/hltEG23EtL1SeededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>23$ GeV (same threshold in EB and EE)

- [hltDiEG12EtL1SeededFilter](../Phase2Menu_Legacy/hltDiEG12EtL1SeededFilter.html):<br> 
select two (`ncandcut=2`) `hltEgammaCandidatesL1Seeded` objects with $p_T>12$ GeV (same threshold in EB and EE)

- [hltDiEG2312IsoClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoClusterShapeL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")`

- [hltDiEG2312IsoClusterShapeSigmavvL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoClusterShapeSigmavvL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2vv")`

- [hltDiEG2312IsoClusterShapeSigmawwL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoClusterShapeSigmawwL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","sigma2ww")`

- [hltDiEG2312IsoHgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoHgcalHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")`

- [hltDiEG2312IsoHEL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoHEL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHoverEL1Seeded")`

- [hltDiEG2312IsoEcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoEcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaEcalPFClusterIsoL1Seeded")`

- [hltDiEG2312IsoHgcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoHgcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHGCalLayerClusterIsoL1Seeded")`

- [hltDiEG2312IsoHcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEG2312IsoHcalIsoL1SeededFilter.html):<br> 
`varTag = cms.InputTag("hltEgammaHcalPFClusterIsoL1Seeded")`

- [hltDiEle2312IsoPixelMatchL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoPixelMatchL1SeededFilter.html):<br> 
Match the EGamma clusters in calorimeters to pixel tracks with `npixelmatchcut = cms.double(1.0)`

- [hltDiEle2312IsoPMS2L1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoPMS2L1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaPixelMatchVarsL1Seeded","s2")`

- [hltDiEle2312IsoGsfOneOEMinusOneOPL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoGsfOneOEMinusOneOPL1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","OneOESuperMinusOneOP")`

- [hltDiEle2312IsoGsfDetaL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoGsfDetaL1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","DetaSeed")`

- [hltDiEle2312IsoGsfDphiL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoGsfDphiL1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaGsfTrackVarsL1Seeded","Dphi")`

- [hltDiEle2312IsoBestGsfNLayerITL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoBestGsfNLayerITL1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsL1Seeded","NLayerIT")`

- [hltDiEle2312IsoBestGsfChi2L1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoBestGsfChi2L1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaBestGsfTrackVarsL1Seeded","Chi2")`

- [hltDiEle2312IsoGsfTrackIsoFromL1TracksL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoGsfTrackIsoFromL1TracksL1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaEleL1TrkIsoL1Seeded")`

- [hltDiEle2312IsoGsfTrackIsoL1SeededFilter](../Phase2Menu_Legacy/hltDiEle2312IsoGsfTrackIsoL1SeededFilter.html): <br> 
`varTag = cms.InputTag("hltEgammaEleGsfTrackIsoL1Seeded")`
