19.**HLT_Mu17_TrkIsoVVL_Mu8_TrkIsoVVL_DZ_FromL1TkMuon**

<span style="color:orange">**L1 seed**</span>: `pSingleTkMuon22`

- [pDoubleTkMuon15_7](../Phase2Menu_Legacy/DoubleTkMuon157.html) : select two muon (`GMTTkMuons`) with $p_T>15$ GeV and $p_T>7$ GeV, respectively - *[Table](../Tables/pDoubleTkMuon15_7.md)*

<span style="color:green">**HLT filters**</span>:

- [hltDoubleMuon7DZ1p0](../Phase2Menu_Legacy/hltDoubleMuon7DZ1p0.html):<br> 
select one (`minN = cms.uint32(1)`) L1 muon (`GMTTkMuons`) with `MaxDz` separation of 1, no $\Delta R$ separation. 

* <span style="color:red">**NOTE**</span>: This HLT module acts on L1 candidates. It looks like a repetition of the L1 trigger seed, which already contains the $\Delta Z$ requirement. In addition, both muons are required to be `triggerType1 = cms.int32(-114), triggerType2 = cms.int32(-114)`

    * <span style="color:red">**NOTE**</span>: Where is `-114` defined? Shouldn't it be `-83`?

- [hltL3fL1DoubleMu155fPreFiltered8](../Phase2Menu_Legacy/hltL3fL1DoubleMu155fPreFiltered8.html):<br>
select two (`minN = cms.uint32(2)`) muons (`hltPhase2L3Muons`) with $p_T>8$ GeV, no $\eta$ cut and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltL3fL1DoubleMu155fFiltered17](../Phase2Menu_Legacy/hltL3fL1DoubleMu155fFiltered17.html):<br>
select one (`minN = cms.uint32(2)`) muon (`hltPhase2L3Muons`) with $p_T>17$ GeV, no $\eta$ cut and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltDiMuon178RelTrkIsoFiltered0p4](../Phase2Menu_Legacy/hltDiMuon178RelTrkIsoFiltered0p4.html):<br>
not clear, to be investigated

- [hltDiMuon178RelTrkIsoFiltered0p4DzFiltered0p2](../Phase2Menu_Legacy/hltDiMuon178RelTrkIsoFiltered0p4DzFiltered0p2.html):<br>
select one (`minN = cms.uint32(1)`) pair of HLT muons (`hltPhase2L3MuonCandidates`) with `MaxDZ` separation of 0.2 and `MinDR` separation 0f 0.001. This acts on top pf the L1 trigger selections, with a looser $\Delta Z$ requirement. In addition, both muons are required to be `triggerType1 = cms.int32(83), triggerType2 = cms.int32(83)`
