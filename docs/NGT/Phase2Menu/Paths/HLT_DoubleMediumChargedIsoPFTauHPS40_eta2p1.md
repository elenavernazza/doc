7.**HLT_DoubleMediumChargedIsoPFTauHPS40_eta2p1**

<span style="color:orange">**L1 seed**</span>: `pDoublePuppiTau52_52`

- [pDoublePuppiTau52_52](../Phase2Menu_Legacy/DoublePuppiTau5252.html) : select two Taus (`CL2Taus`) with $p_T>52$ GeV - *[Table](../Tables/pDoublePuppiTau52_52.md)*

<span style="color:green">**HLT filters**</span>:

- [hltPreDoublePFTauHPS](../Phase2Menu_Legacy/hltPreDoublePFTauHPS.html):<br> 
prescaler with `offset = cms.uint32(0)`

    * <span style="color:red">**NOTE**</span>: Does this have a real effect?

- [hltHpsSelectedPFTausTrackFinding](../Phase2Menu_Legacy/hltHpsSelectedPFTausTrackFinding.html):<br> 
`cut = cms.string('pt > 0'),
discriminator = cms.InputTag("hltHpsPFTauTrackFindingDiscriminator"),
selectionCut = cms.double(0.5),
src = cms.InputTag("hltHpsPFTauProducer")`

I assume it looks for a track matching the Tau within $\Delta R = 0.5$

- [hltHpsPFTauTrack](../Phase2Menu_Legacy/hltHpsPFTauTrack.html):<br> 
select single HPS Tau (`hltHpsPFTauProducer`) with no $p_T$ cut, with $-1<\eta<2.5$ and `triggerType=84`.

    * <span style="color:red">**NOTE**</span>: The minimum eta value is correct: when it is negative, the condition is not applied. 

    * <span style="color:red">**NOTE**</span>: Are we selecting only one tau? The path indicates two taus.

- [hltHpsSelectedPFTausTrackPt1MediumChargedIsolation](../Phase2Menu_Legacy/hltHpsSelectedPFTausTrackPt1MediumChargedIsolation.html):<br> 
`cut = cms.string('pt > 0'),
discriminator = cms.InputTag("hltHpsPFTauMediumAbsOrRelChargedIsolationDiscriminator"),
selectionCut = cms.double(0.5),
src = cms.InputTag("hltHpsPFTauProducer")` 

I assume it looks for Taua with 0.5 relative isolation

- [hltHpsDoublePFTau40TrackPt1MediumChargedIsolation](../Phase2Menu_Legacy/hltHpsDoublePFTau40TrackPt1MediumChargedIsolation.html):<br> 
select two HPS Taus (`hltHpsSelectedPFTausTrackPt1MediumChargedIsolation`) with $p_T>40$ GeV, with $-1<\eta<2.1$ and `triggerType=84`

    * <span style="color:red">**NOTE**</span>: The maximum eta value goes from 2.5 to 2.1, since the tau reconstruction in Phase 1 is based on tracking information. This should be changed for Phase 2 to extend the taus up to the HGCAL coverage.