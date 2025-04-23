18.**HLT_IsoMu24_FromL1TkMuon**

<span style="color:orange">**L1 seed**</span>: `pSingleTkMuon22`

- [pSingleTkMuon22](../Phase2Menu_Legacy/SingleTkMuon22.html) : select one muon (`GMTTkMuons`) with $p_T>22$ GeV - *[Table](../Tables/pSingleTkMuon22.md)*

<span style="color:green">**HLT filters**</span>:

- [hltL3fL1TkSingleMu22L3Filtered24Q](../Phase2Menu_Legacy/hltL3fL1TkSingleMu22L3Filtered24Q.html):<br> 
select one (`minN = cms.uint32(1)`) muon (`hltPhase2L3Muons`) with $p_T>24$ GeV, no $\eta$ cut and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltL3crIsoL1TkSingleMu22L3f24QL3pfecalIsoFiltered0p41](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22L3f24QL3pfecalIsoFiltered0p41.html) --- *[HLTMuonGenericFilter](https://github.com/cms-sw/cmssw/blob/master/HLTrigger/Egamma/plugins/HLTGenericFilter.cc)*:<br> 
select muon with ECAL isolation within $\Delta R < 0.3$ ([`hltPhase2L3MuonsEcalIsodR0p3dRVeto0p000`](../Phase2Menu_Legacy/hltPhase2L3MuonsEcalIsodR0p3dRVeto0p000.html)) below 0.41 (same threshold in barrel and endcap)

- [hltL3crIsoL1TkSingleMu22L3f24QL3pfhcalIsoFiltered0p40](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22L3f24QL3pfhcalIsoFiltered0p40.html) --- *[HLTMuonGenericFilter](https://github.com/cms-sw/cmssw/blob/master/HLTrigger/Egamma/plugins/HLTGenericFilter.cc)*:<br> 
select muon with HCAL isolation within $\Delta R < 0.3$ ([`hltPhase2L3MuonsHcalIsodR0p3dRVeto0p000`](../Phase2Menu_Legacy/hltPhase2L3MuonsHcalIsodR0p3dRVeto0p000.html)) below 0.4 (same threshold in barrel and endcap)

- [hltL3crIsoL1TkSingleMu22L3f24QL3pfhgcalIsoFiltered4p70](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22L3f24QL3pfhgcalIsoFiltered4p70.html) --- *[HLTMuonGenericFilter](https://github.com/cms-sw/cmssw/blob/master/HLTrigger/Egamma/plugins/HLTGenericFilter.cc)*:<br> 
select muon with HCAL isolation within $\Delta R < 0.2$ ([`hltPhase2L3MuonsHgcalLCIsodR0p2dRVetoEM0p00dRVetoHad0p02minEEM0p00minEHad0p00`](../Phase2Menu_Legacy/hltPhase2L3MuonsHgcalLCIsodR0p2dRVetoEM0p00dRVetoHad0p02minEEM0p00minEHad0p00.html)) below 4.7

- [hltL3crIsoL1TkSingleMu22L3f24QL3trkIsoRegionalNewFiltered0p07EcalHcalHgcalTrk](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22L3f24QL3trkIsoRegionalNewFiltered0p07EcalHcalHgcalTrk.html) --- *[LTMuonIsoFilter](https://github.com/cms-sw/cmssw/blob/master/HLTrigger/Muon/plugins/HLTMuonIsoFilter.cc)*:<br> 
not clear, to be investigated
