9.**HLT_DoublePFPuppiJets128_DoublePFPuppiBTagDeepCSV_2p4**

<span style="color:orange">**L1 seed**</span>: `pDoublePuppiJet112_112`

- [pDoublePuppiJet112_112](../Phase2Menu_Legacy/DoublePuppiJet112112.html) : select two PUPPI jets (`CL2JetsSC4`) with $p_T>112$ GeV - *[Table](../Tables/pDoublePuppiJet112_112.md)*

<span style="color:green">**HLT filters**</span>:

- [hltGoodOfflinePrimaryVertices](../Phase2Menu_Legacy/hltGoodOfflinePrimaryVertices.html):<br>
`cut = cms.string('!isFake && ndof >= 4.0 && abs(z) <= 24.0 && abs(position.Rho) <= 2.0'),
filter = cms.bool(False),
src = cms.InputTag("hltOfflinePrimaryVertices")`

    * <span style="color:red">**NOTE**</span>: Why is the filter to False?

- [hltDoublePFPuppiJets128MaxEta2p4](../Phase2Menu_Legacy/hltDoublePFPuppiJets128MaxEta2p4.html):<br> 
select two AK4 PF PUPPI jets (`hltAK4PFPuppiJetsCorrected`) with $p_T>128$ GeV, $|\eta|<2.4$ and `triggerType=86`

- [hltDoublePFPuppiJets128Eta2p4MaxDeta1p6](../Phase2Menu_Legacy/hltDoublePFPuppiJets128Eta2p4MaxDeta1p6.html):<br> 
require maximum deltaR of (`MaxDelR = cms.double(1000.0)`) and deltaEta (`MaxDeta = cms.double(1.6)`)

- [hltPFPuppiJetForBtagSelectorEta2p4](../Phase2Menu_Legacy/hltPFPuppiJetForBtagSelectorEta2p4.html):<br> 
select one AK4 PF PUPPI jets (`hltAK4PFPuppiJetsCorrected`) with $p_T>30$ GeV, $|\eta|<2.4$ and `triggerType=86`

    * <span style="color:red">**NOTE**</span>: We have already selected two jets with $p_T>128$ GeV, why are we applying again the same filter with a looser cut?

- [hltBTagPFPuppiDeepCSV0p865DoubleEta2p4](../Phase2Menu_Legacy/hltBTagPFPuppiDeepCSV0p865DoubleEta2p4.html):<br> 
select two jets with a b-tagging DeepCSV score (`JetTags = cms.InputTag("hltDeepCombinedSecondaryVertexBJetTagsPFPuppiModEta2p4","probb")`) higher than 0.865 (`MinTag = cms.double(0.865)`). The jets and b-jets are matched by deltaR requirement (`MatchJetsByDeltaR = cms.bool(True)` and `MaxJetDeltaR = cms.double(0.1)`)