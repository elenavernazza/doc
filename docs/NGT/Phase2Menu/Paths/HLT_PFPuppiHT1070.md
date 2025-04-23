26.**HLT_PFPuppiHT1070**

<span style="color:orange">**L1 seed**</span>: `pPuppiHT450`

- [pPuppiHT450](../Phase2Menu_Legacy/PuppiHT450.html) : select scalar sum (`CL2HtSum`) with $H_T>450$ GeV  - *[Table](../Tables/pPuppiHT450.md)*

<span style="color:green">**HLT filters**</span>:

- [hltGoodOfflinePrimaryVertices](../Phase2Menu_Legacy/hltGoodOfflinePrimaryVertices.html):<br>
`cut = cms.string('!isFake && ndof >= 4.0 && abs(z) <= 24.0 && abs(position.Rho) <= 2.0'),
filter = cms.bool(False),
src = cms.InputTag("hltOfflinePrimaryVertices")`

    * <span style="color:red">**NOTE**</span>: Why is the filter to False?

- [hltPFPuppiHT1070](../Phase2Menu_Legacy/hltPFPuppiHT1070.html):<br> 
select PUPPI scalar sum (`hltPFPuppiHT`) above $H_T>1070$ GeV