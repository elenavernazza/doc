32.**HLT_TriMu_10_5_5_DZ_FromL1TkMuon**

<span style="color:orange">**L1 seed**</span>: *NOTHING*

    * <span style="color:red">**NOTE**</span>: This HLT path doesn't have any L1 seed.

<span style="color:green">**HLT filters**</span>:

- [hltTripleMuon3DZ1p0](../Phase2Menu_Legacy/hltTripleMuon3DZ1p0.html):<br> 
select three (`minN = cms.uint32(3)`) L1 muons (`GMTTkMuons`) with `MaxDz` separation of 1, no $\Delta R$ separation. In addition, both muons are required to be `triggerType1 = cms.int32(-114), triggerType2 = cms.int32(-114)`

    * <span style="color:red">**NOTE**</span>: Where is `-114` defined? Shouldn't it be `-83`?

- [hltTripleMuon3DR0](../Phase2Menu_Legacy/hltTripleMuon3DR0.html):<br>
select three (`minN = cms.uint32(3)`) L1 muons (`GMTTkMuons`) with no `MaxDz` separation, $\Delta R>0$ separation. In addition, both muons are required to be `triggerType1 = cms.int32(-114), triggerType2 = cms.int32(-114)`

    * <span style="color:red">**NOTE**</span>: Where is `-114` defined? Shouldn't it be `-83`?

    * <span style="color:red">**NOTE**</span>: Are there cases when $\Delta R$ is negative? How should a minimum value of 0 make the difference?

- [hltL3fL1TkTripleMu533PreFiltered555](../Phase2Menu_Legacy/hltL3fL1TkTripleMu533PreFiltered555.html):<br>
select three (`minN = cms.uint32(3)`) muons (`hltPhase2L3Muons`) with $p_T>5$ GeV, $|\eta|<2.5$ and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltL3fL1TkTripleMu533L3Filtered1055](../Phase2Menu_Legacy/hltL3fL1TkTripleMu533L3Filtered1055.html):<br>
select one (`minN = cms.uint32(1)`) muon (`hltPhase2L3Muons`) with $p_T>10$ GeV, $|\eta|<2.5$ and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltL3fL1TkTripleMu533L31055DZFiltered0p2](../Phase2Menu_Legacy/hltL3fL1TkTripleMu533L31055DZFiltered0p2.html):<br>
select three (`minN = cms.uint32(3)`) HLT muons (`hltPhase2L3MuonCandidates`) with `MaxDZ` separation of 0.2 and `MinDR` separation 0f 0.001. In addition, both muons are required to be `triggerType1 = cms.int32(83), triggerType2 = cms.int32(83)`
