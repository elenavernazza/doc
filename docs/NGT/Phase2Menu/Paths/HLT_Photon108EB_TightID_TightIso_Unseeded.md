29.**LT_Photon108EB_TightID_TightIso_Unseeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleIsoTkPho36`

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleIsoTkPho36](../Phase2Menu_Legacy/SingleIsoTkPho36.html) : select one EGamma (`CL2Photons`) with $p_T>36$ GeV  - *[Table](../Tables/pSingleIsoTkPho36.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperUnseeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html):<br> 
select `hltEgammaCandidatesUnseeded` with isolation condition

- [hltEG108EtUnseededFilter](../Phase2Menu_Legacy/hltEG108EtUnseededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>108.0$ GeV in the barrel (the endcap is removed by putting a very high threshold `etcutEE = cms.double(9999999.0)`)

- [hltPhoton108EBTightIDTightIsoClusterShapeUnseededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoClusterShapeUnseededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaClusterShapeUnseeded","sigmaIEtaIEta5x5")` above 0.01 in the barrel

- [hltPhoton108EBTightIDTightIsoHEUnseededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoHEUnseededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHoverEUnseeded")` above 0.05 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)

- [hltPhoton108EBTightIDTightIsoEcalIsoUnseededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoEcalIsoUnseededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaEcalPFClusterIsoUnseeded")` between 0.02 and 2.5 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)

- [hltPhoton108EBTightIDTightIsoHcalIsoUnseededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoHcalIsoUnseededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHcalPFClusterIsoUnseeded")` between 0.02 and 3.8 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and between 0.02 ands barrel 6 ($1 < \lvert\eta\rvert < 1.479$)
