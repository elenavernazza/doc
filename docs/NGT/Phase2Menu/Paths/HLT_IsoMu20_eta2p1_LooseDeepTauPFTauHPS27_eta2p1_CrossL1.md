17.**HLT_IsoMu20_eta2p1_LooseDeepTauPFTauHPS27_eta2p1_CrossL1**

<span style="color:orange">**L1 seed**</span>: `pPuppiTauTkMuon42_18`

- [pPuppiTauTkMuon42_18](../Phase2Menu_Legacy/PuppiTauTkMuon4218.html) : select one muon (`GMTTkMuons`) with $p_T>18$ GeV and one Tau (`CL2Taus`) with $p_T>42$ GeV - *[Table](../Tables/pPuppiTauTkMuon42_18.md)*

<span style="color:green">**HLT filters**</span>:

- [hltL3fL1TkSingleMu18Filtered20](../Phase2Menu_Legacy/hltL3fL1TkSingleMu18Filtered20.html):<br> 
select one (`minN = cms.uint32(1)`) muon (`hltPhase2L3Muons`) with $p_T>20$ GeV, $|\eta|<2.1$ and at least 1 hit in the muon stations (`minMuonStations = cms.int32(1)`)

- [hltL3crIsoL1TkSingleMu22EcalIso0p41](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22EcalIso0p41.html):<br> 
select the muons with isolation in ECAL (`varTag = cms.InputTag("hltPhase2L3MuonsEcalIsodR0p3dRVeto0p000")`) less than 0.41 (same threshold in EB and EE)

- [hltL3crIsoL1TkSingleMu22HcalIso0p40](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22HcalIso0p40.html):<br> 
select the muons with isolation in HCAL (`varTag = cms.InputTag("hltPhase2L3MuonsHcalIsodR0p3dRVeto0p000")`) less than 0.40 (same threshold in HB and HE)

- [hltL3crIsoL1TkSingleMu22HgcalIso4p70](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22HgcalIso4p70.html):<br> 
select the muons with isolation in HGCAL (`hltPhase2L3MuonsHgcalLCIsodR0p2dRVetoEM0p00dRVetoHad0p02minEEM0p00minEHad0p00`) less than 4.7 

- [hltL3crIsoL1TkSingleMu22TrkIsoRegionalNewFiltered0p07EcalHcalHgcalTrk](../Phase2Menu_Legacy/hltL3crIsoL1TkSingleMu22TrkIsoRegionalNewFiltered0p07EcalHcalHgcalTrk.html):<br> 
not clear

- [hltHpsSelectedPFTausTrackFinding](../Phase2Menu_Legacy/hltHpsSelectedPFTausTrackFinding.html):<br> 
`cut = cms.string('pt > 0'),
discriminator = cms.InputTag("hltHpsPFTauTrackFindingDiscriminator"),
selectionCut = cms.double(0.5),
src = cms.InputTag("hltHpsPFTauProducer")`

I assume it looks for a track matching the Tau within $\Delta R = 0.5$

- [hltHpsPFTauTrack](../Phase2Menu_Legacy/hltHpsPFTauTrack.html):<br> 
select single HPS Tau (`hltHpsPFTauProducer`) with no $p_T$ cut, with $-1<\eta<2.5$ and `triggerType=84`

    * <span style="color:red">**NOTE**</span>: Is the minimum eta value correct? Shouldn't it be -2.5? 

- [hltHpsSelectedPFTauLooseTauWPDeepTau](../Phase2Menu_Legacy/hltHpsSelectedPFTauLooseTauWPDeepTau.html):<br>
`cut = cms.string('pt > 27 && abs(eta) < 2.1'),
discriminator = cms.InputTag("hltHpsPFTauDeepTauProducer","VSjet"),
workingPoints = cms.vstring('double t1 = 0.5419, t2 = 0.4837, t3 = 0.050, x1 = 27, x2 = 100, x3 = 300; if (pt <= x1) return t1; if (pt >= x3) return t3; if (pt < x2) return (t2 - t1) / (x2 - x1) * (pt - x1) + t1; return (t3 - t2) / (x3 - x2) * (pt - x2) + t2;')`

I assume it looks for Tau with 0.5 relative isolation

    | $p_T$ value           | DeepTauVSjet Loose WP                                     |
    |-----------------------|-----------------------------------------------------------|
    | $p_T\leq27$ GeV       | 0.5419                                                    |
    | $27<p_T<100$ GeV      | 0.5419 + (0.4837 - 0.5419) / (100 - 27) * ($p_T$ - 27)    |
    | $100p_T<300$ GeV      | 0.4837 + (0.050 - 0.4837) / (300 - 100) * ($p_T$ - 100)   |
    | $p_T\geq300$ GeV      | 0.050                                                     |

<figure markdown="span">
  ![DeepTauVSjet WP](../../Figures/WPs.png){ width="500", align=left }
</figure>

    * <span style="color:red">**NOTE**</span>: Why is the Medium WP at a lower level than the Loose WP for $p_T$ around 100 GeV ?

- [hltHpsPFTau27LooseTauWPDeepTau](../Phase2Menu_Legacy/hltHpsPFTau27LooseTauWPDeepTau.html):<br> 
select single HPS Tau (`hltHpsSelectedPFTauLooseTauWPDeepTau`) with $p_T>27$ GeV, with $-1<\eta<2.1$ and `triggerType=84`

    * <span style="color:red">**NOTE**</span>: The maximum eta value goes from 2.5 to 2.1, since the tau reconstruction in Phase 1 is based on tracking information. This should be changed for Phase 2 to extend the taus up to the HGCAL coverage.