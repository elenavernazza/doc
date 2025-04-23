23.**HLT_PFHT200PT30_QuadPFPuppiJet_70_40_30_30_TriplePFPuppiBTagDeepFlavour_2p4**

<span style="color:orange">**L1 seed**</span>: `pPuppiHT400 and pQuadJet70_55_40_40`

- [pPuppiHT400](../Phase2Menu_Legacy/PuppiHT400.html) : select scalar sum (`CL2HtSum`) with $H_T>400$ GeV - *[Table](../Tables/pPuppiHT400.md)*
- [pQuadJet70_55_40_40](../Phase2Menu_Legacy/QuadJet70554040.html) : select four jets (`CL2JetsSC4`) with $p_T>70,\;55\,40\;40$ GeV, respectively - *[Table](../Tables/pQuadJet70_55_40_40.md)*

<span style="color:green">**HLT filters**</span>:

- [hltGoodOfflinePrimaryVertices](../Phase2Menu_Legacy/hltGoodOfflinePrimaryVertices.html):<br>
`cut = cms.string('!isFake && ndof >= 4.0 && abs(z) <= 24.0 && abs(position.Rho) <= 2.0'),
filter = cms.bool(False),
src = cms.InputTag("hltOfflinePrimaryVertices")`

    * <span style="color:red">**NOTE**</span>: Why is the filter to False?

- [hltPFPuppiCentralJetQuad30MaxEta2p4](../Phase2Menu_Legacy/hltPFPuppiCentralJetQuad30MaxEta2p4.html):<br>
select four (`minN = cms.uint32(4)`) AK4 PUPPI b-jets (`hltAK4PFPuppiJetsCorrected`) with $p_T>30$ GeV, $|\eta|<2.4$ and `triggerType=86`.

- [hlt1PFPuppiCentralJet70MaxEta2p4](../Phase2Menu_Legacy/hlt1PFPuppiCentralJet70MaxEta2p4.html):<br>
select one (`minN = cms.uint32(1)`) AK4 PUPPI b-jet (`hltAK4PFPuppiJetsCorrected`) with $p_T>70$ GeV, $|\eta|<2.4$ and `triggerType=86`.

- [hlt2PFPuppiCentralJet40MaxEta2p4](../Phase2Menu_Legacy/hlt2PFPuppiCentralJet40MaxEta2p4.html):<br>
select two (`minN = cms.uint32(2)`) AK4 PUPPI b-jets (`hltAK4PFPuppiJetsCorrected`) with $p_T>40$ GeV, $|\eta|<2.4$ and `triggerType=86`.

    * <span style="color:red">**NOTE**</span>: Is there a reason why we first select one jet at 70 GeV rather than two jets at 40 GeV?

- [hltPFPuppiCentralJetsQuad30HT200MaxEta2p4](../Phase2Menu_Legacy/hltPFPuppiCentralJetsQuad30HT200MaxEta2p4.html):<br>
select scalar sum of all jets with $p_T>30$ GeV in $|\eta|<2.4$ ([`hltHtMhtPFPuppiCentralJetsQuadC30MaxEta2p4`](../Phase2Menu_Legacy/hltHtMhtPFPuppiCentralJetsQuadC30MaxEta2p4.html)) above 200 GeV

- [hltPFPuppiJetForBtagSelectorEta2p4](../Phase2Menu_Legacy/hltPFPuppiJetForBtagSelectorEta2p4.html):<br>
select one (`minN = cms.uint32(1)`) AK4 PUPPI b-jets (`hltAK4PFPuppiJetsCorrected`) with $p_T>30$ GeV, $|\eta|<2.4$ and `triggerType=86`.

    * <span style="color:red">**NOTE**</span>: We have already selected four jets, why are we applying again the same filter with a looser cut?

- [hltBTagPFPuppiDeepFlavour0p375Eta2p4TripleEta2p4](../Phase2Menu_Legacy/hltBTagPFPuppiDeepFlavour0p375Eta2p4TripleEta2p4.html):<br>
select three (`MinJets = cms.int32(3)`) b-jets (`hltPFPuppiJetForBtagEta2p4`, `TriggerType = cms.int32(86)`) with a b-tagging DeepFlavour score (`JetTags = cms.InputTag("hltPfDeepFlavourJetTagsModEta2p4","probb")`) higher than 0.375 (`MinTag = cms.double(0.375)`).