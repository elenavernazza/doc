27.**HLT_PFPuppiMETTypeOne140_PFPuppiMHT140**

<span style="color:orange">**L1 seed**</span>: `pPuppiMET200`

- [pPuppiMET200](../Phase2Menu_Legacy/PuppiMET200.html) : select scalar sum (`CL2EtSum`) with $p_T^{miss}>200$ GeV  - *[Table](../Tables/pPuppiMET200.md)*

<span style="color:green">**HLT filters**</span>:

- [hltGoodOfflinePrimaryVertices](../Phase2Menu_Legacy/hltGoodOfflinePrimaryVertices.html):<br>
`cut = cms.string('!isFake && ndof >= 4.0 && abs(z) <= 24.0 && abs(position.Rho) <= 2.0'),
filter = cms.bool(False),
src = cms.InputTag("hltOfflinePrimaryVertices")`

    * <span style="color:red">**NOTE**</span>: Why is the filter to False?

- [hltGoodOfflinePrimaryVertices](../Phase2Menu_Legacy/hltGoodOfflinePrimaryVertices.html):<br>
`cut = cms.string('!isFake && ndof >= 4.0 && abs(z) <= 24.0 && abs(position.Rho) <= 2.0'),
filter = cms.bool(False),
src = cms.InputTag("hltOfflinePrimaryVertices")`

    * <span style="color:red">**NOTE**</span>: Why is the filter to False?

    * <span style="color:red">**NOTE**</span>: This module is called twice, but maybe it's not really a filter.

- [hltPFPuppiMETTypeOne140](../Phase2Menu_Legacy/hltPFPuppiMETTypeOne140.html):<br> 
select PUPPI missing $E_T$ (`hltPFPuppiMETTypeOne`, `triggerType = cms.int32(87)`) above $E_T>140$ GeV

- [hltPFPuppiMHT140](../Phase2Menu_Legacy/hltPFPuppiMHT140.html):<br>
select PUPPI scalar sum (`hltPFPuppiMHT`) above $H_T>140$ GeV

