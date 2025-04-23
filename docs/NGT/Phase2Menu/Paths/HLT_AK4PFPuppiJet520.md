1.**HLT_AK4PFPuppiJet520**

<span style="color:orange">**L1 seed**</span>: `pSinglePuppiJet230`

- [pSinglePuppiJet230](../Phase2Menu_Legacy/SinglePuppiJet230.html) : select single PUPPI jet (`CL2JetsSC4`) with $p_T>230$ GeV - *[Table](../Tables/pSinglePuppiJet230.md)*

<span style="color:green">**HLT filters**</span>:

- [hltGoodOfflinePrimaryVertices](../Phase2Menu_Legacy/hltGoodOfflinePrimaryVertices.html):<br>
`cut = cms.string('!isFake && ndof >= 4.0 && abs(z) <= 24.0 && abs(position.Rho) <= 2.0'),
filter = cms.bool(False),
src = cms.InputTag("hltOfflinePrimaryVertices")`

    * <span style="color:red">**NOTE**</span>: Why is the filter to False?

- [hltSingleAK4PFPuppiJet520](../Phase2Menu_Legacy/hltSingleAK4PFPuppiJet520.html):<br> 
select single AK4 PF PUPPI jet (`hltAK4PFPuppiJetsCorrected`) with $p_T>520$ GeV, $|\eta|<5$ and `triggerType=85`. The `triggerType` condition is used for the jet identification and defined [here](https://github.com/cms-sw/cmssw/blob/master/HLTriggerOffline/Egamma/python/TriggerTypeDefs_cfi.py#L39). In the current menu it is used for b-jets (`triggerType=86`) and taus (`triggerType=84`) as well