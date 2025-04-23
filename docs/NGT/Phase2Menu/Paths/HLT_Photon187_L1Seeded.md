30.**HLT_Photon187_L1Seeded**

<span style="color:orange">**L1 seed**</span>: no explicit L1 path, using L1TTkEmFilter

- [l1tTkEmSingle51Filter](../Phase2Menu_Legacy/l1tTkEmSingle51Filter.html) : select one electromagnetic cluster (`L1TkEmEB` and `L1TkEmEE`) with maximum tracker isolation (`TrkIsolation = cms.vdouble(99999.0, 99999.0)`), with $p_T>187$ GeV - *[Table](../Tables/l1tTkEmSingle51Filter.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltEG187EtL1SeededFilter](../Phase2Menu_Legacy/hltEG187EtL1SeededFilter.html):<br>
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>187.0$ GeV (same threshold in barrel and endcap)

- [hltPhoton187HgcalHEL1SeededFilter](../Phase2Menu_Legacy/hltPhoton187HgcalHEL1SeededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHGCALIDVarsL1Seeded","hForHOverE")` above 0.055 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)

- [hltPhoton187HEL1SeededFilter](../Phase2Menu_Legacy/hltPhoton187HEL1SeededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHoverEL1Seeded")` above 0.09 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)
