20.**HLT_Mu37_Mu27_FromL1TkMuon**

<span style="color:orange">**L1 seed**</span>: *NOTHING*

    * <span style="color:red">**NOTE**</span>: This HLT path doesn't have any L1 seed!

<span style="color:green">**HLT filters**</span>:

- [hltDoubleMuon7DZ1p0](../Phase2Menu_Legacy/hltDoubleMuon7DZ1p0.html):<br> 
select one (`minN = cms.uint32(1)`) L1 muon (`GMTTkMuons`) with `MaxDz` separation of 1, no $\Delta R$ separation. This looks like a repetition of the L1 trigger seed, which already contains the $\Delta Z$ requirement. In addition, both muons are required to be `triggerType1 = cms.int32(-114), triggerType2 = cms.int32(-114)`

    * <span style="color:red">**NOTE**</span>: Where is `-114` defined? Shouldn't it be `-83`?

- [hltL3fL1DoubleMu155fPreFiltered27](../Phase2Menu_Legacy/hltL3fL1DoubleMu155fPreFiltered27.html):<br>
select two (`minN = cms.uint32(2)`) muons (`hltPhase2L3Muons`) with $p_T>27$ GeV, no $\eta$ cut and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltL3fL1DoubleMu155fFiltered37](../Phase2Menu_Legacy/hltL3fL1DoubleMu155fFiltered37.html):<br>
select one (`minN = cms.uint32(2)`) muon (`hltPhase2L3Muons`) with $p_T>37$ GeV, no $\eta$ cut and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)