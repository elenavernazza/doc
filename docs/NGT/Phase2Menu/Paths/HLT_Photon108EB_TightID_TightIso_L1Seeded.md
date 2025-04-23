28.**HLT_Photon108EB_TightID_TightIso_L1Seeded**

<span style="color:orange">**L1 seed**</span>: `pSingleEGEle51 or pSingleIsoTkPho36`

- [pSingleEGEle51](../Phase2Menu_Legacy/SingleEGEle51.html) : select one EGamma (`CL2Photons`) with $p_T>51$ GeV - *[Table](../Tables/pSingleEGEle51.md)*
- [pSingleIsoTkPho36](../Phase2Menu_Legacy/SingleIsoTkPho36.html) : select one EGamma (`CL2Photons`) with $p_T>36$ GeV  - *[Table](../Tables/pSingleIsoTkPho36.md)*

<span style="color:green">**HLT filters**</span>:

- [hltEgammaCandidatesWrapperL1Seeded](../Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html):<br> 
select `hltEgammaCandidatesL1Seeded` with isolation condition

- [hltEG108EtL1SeededFilter](../Phase2Menu_Legacy/hltEG108EtL1SeededFilter.html):<br> 
select one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>108.0$ GeV in the barrel (the endcap is removed by putting a very high threshold `etcutEE = cms.double(9999999.0)`)

- [hltPhoton108EBTightIDTightIsoClusterShapeL1SeededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoClusterShapeL1SeededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaClusterShapeL1Seeded","sigmaIEtaIEta5x5")` above 0.01 in the barrel

- [hltPhoton108EBTightIDTightIsoHEL1SeededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoHEL1SeededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHoverEL1Seeded")` above 0.05 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)

- [hltPhoton108EBTightIDTightIsoEcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoEcalIsoL1SeededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaEcalPFClusterIsoL1Seeded")` between 0.02 and 2.5 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and barrel 2 ($1 < \lvert\eta\rvert < 1.479$)

- [hltPhoton108EBTightIDTightIsoHcalIsoL1SeededFilter](../Phase2Menu_Legacy/hltPhoton108EBTightIDTightIsoHcalIsoL1SeededFilter.html):<br>
require `varTag = cms.InputTag("hltEgammaHcalPFClusterIsoL1Seeded")` between 0.02 and 3.8 in barrel 1 ($0 < \lvert\eta\rvert < 1$) and between 0.02 ands barrel 6 ($1 < \lvert\eta\rvert < 1.479$)
