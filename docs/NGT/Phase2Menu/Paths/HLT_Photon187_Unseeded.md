31.**HLT_Photon187_Unseeded**

<span style="color:orange">**L1 seed**</span>: no explicit L1 path, using L1TTkEmFilter

- [l1tTkEmSingle51Filter](../Phase2Menu_Legacy/l1tTkEmSingle51Filter.html) : select one electromagnetic cluster (`L1TkEmEB` and `L1TkEmEE`) with maximum tracker isolation (`TrkIsolation = cms.vdouble(99999.0, 99999.0)`), with $p_T>187$ GeV - *[Table](../Tables/l1tTkEmSingle51Filter.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperUnseeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html):<br> 
select `hltEgammaCandidatesUnseeded` with isolation condition

- [hltEG187EtUnseededFilter](../Phase2Menu_Legacy/hltEG187EtUnseededFilter.html):<br>
select one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>187.0$ GeV (same threshold in barrel and endcap)

- [hltPhoton187HgcalHEUnseededFilter](../Phase2Menu_Legacy/hltPhoton187HgcalHEUnseededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHGCALIDVarsUnseeded","hForHOverE")` above 0.055 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)

- [hltPhoton187HEUnseededFilter](../Phase2Menu_Legacy/hltPhoton187HEUnseededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHoverEUnseeded")` above 0.09 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)
