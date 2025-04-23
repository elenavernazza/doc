21.**HLT_Mu50_FromL1TkMuon**

<span style="color:orange">**L1 seed**</span>: `pSingleTkMuon22`

- [pSingleTkMuon22](../Phase2Menu_Legacy/SingleTkMuon22.html) : select one muon (`GMTTkMuons`) with $p_T>22$ GeV - *[Table](../Tables/pSingleTkMuon22.md)*

<span style="color:green">**HLT filters**</span>:

- [hltL3fL1TkSingleMu22L3Filtered50Q](../Phase2Menu_Legacy/hltL3fL1TkSingleMu22L3Filtered50Q.html):<br>
select one (`minN = cms.uint32(1)`) muon (`hltPhase2L3Muons`) with $p_T>50$ GeV, no $\eta$ cut and at least 1 hit in the muon stations (`minMuonStations = cms.int32`)