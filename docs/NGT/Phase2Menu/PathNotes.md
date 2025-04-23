<!-- # Paths and descriptions - Legacy HLT Menu

1. HLT_AK4PFPuppiJet520

    - Sequence **HLTBeginSequence** : same everywhere
        - HLTTriggerTypeFilter
        - BeamSpotOnlineProducer

    - L1 seed: [pSinglePuppiJet230](./Phase2Menu_Legacy/SinglePuppiJet230.html)
    This seed should select the events containing at L1 a single PUPPI jet with $p_T>230$ GeV (but I don't see it in the path).
    
    | Selection                                     | Value                 |
    |-----------------------------------------------|-----------------------|
    | $\eta$ region                                 | $\|\eta\| < 2.4$      |
    | `GTTPrimaryVert`                              | ?                     |
    | Different MinPt for different eta regions:    |                       |
    |    - $0<\|\eta\|<1.5$                         | $p_T>166.1$ GeV       |
    |    - $1.5<\|\eta\|<2.4$                       | $p_T>128.51$ GeV      |
    |    - $\|\eta\|>2.4$                           | $p_T>139.1$ GeV       |

    - Sequence **HLTRawToDigiSequence** : same everywhere
        - HGCalRawToDigiFake
        - EcalRawToDigi 
        - HcalRawToDigi
        - CSCDCCUnpacker
        - DTuROSRawToDigi
        - GEMRawToDigiModule

    - Sequence **HLTHgcalLocalRecoSequence** : 
        - hltHGCalUncalibRecHit
        - hltHGCalRecHit
        - hltHgcalLayerClustersEE
        - hltHgcalLayerClustersHSci
        - hltHgcalLayerClustersHSi
        - hltHgcalMergeLayerClusters

    - Sequence **HLTLocalrecoSequence** : 
        - BunchSpacingProducer
        - Sequence HLTCalolocalrecoSequence :
            - Sequence HLTDoFullUnpackingEgammaEcalSequence :
                - EcalRawToDigi is done twice (why?)
                - BunchSpacingProducer is also done twice (why?)
            - Sequence HLTDoLocalHcalSequence
    
    - Sequence **HLTTrackingSequence** :
        - Sequence HLTItLocalRecoSequence 
        - Sequence HLTOtLocalRecoSequence
        - ClusterCheckerEDProducer
        - Sequence HLTPhase2PixelTracksSequence
        - PixelVertexProducer
        - Sequence HLTInitialStepSequence
        - Sequence HLTHighPtTripletStepSequence

    - Sequence **HLTMuonsSequence** :
        - Sequence HLTL2MuonsFromL1TkSequence
        - Sequence HLTPhase2L3OISequence
        - Sequence HLTPhase2L3FromL1TkSequence
        - Sequence HLTIter0Phase2L3FromL1TkSequence
        - Sequence HLTIter2Phase2L3FromL1TkSequence
        - Sequence HLTPhase2L3MuonsSequence

    - Sequence **HLTParticleFlowSequence**
        - Sequence HLTParticleFlowClusterSequence
        - Sequence HLTIterTICLSequence
        - Sequence HLTVertexRecoSequence
        - Sequence HLTParticleFlowSuperClusteringSequence
        - Sequence HLTCaloTowersRecSequence
        - Sequence HLTParticleFlowRecoSequence

    - Sequence **HLTAK4PFPuppiJetsReconstruction**

    - HLT filter: [hltSingleAK4PFPuppiJet520](./Phase2Menu_Legacy/hltSingleAK4PFPuppiJet520.html)
    This seed should select the events containing at HLT a single AK4 PF PUPPI jet with $p_T>520$ GeV.

    | Selection                                     | Value                 |
    |-----------------------------------------------|-----------------------|
    | $\eta$ region                                 | $\|\eta\| < 5.0$      |
    | MinPt                                         | $p_T>520$             |
    | triggerType                                   | 85 ?                  |

    - Sequence **HLTEndSequence**

2. HLT_Diphoton30_23_IsoCaloId_L1Seeded

    - Sequence **HLTBeginSequence** : same everywhere

    - Sequence **HLTDiphoton3023IsoCaloIdL1SeededSequence**
        - Sequence HLTL1Sequence
        - L1 seed: [pDoubleEGEle37_24](./Phase2Menu_Legacy/DoubleEGEle3724.html) OR [pDoubleIsoTkPho22_12](./Phase2Menu_Legacy/DoubleIsoTkPho2212.html)
        This seed should select the events containing at L1 two photons with $p_T>30$ and $p_T>23$ GeV, respectively (but I don't see it clearly in the path).
    
        | Selection                                     | Value                 |
        |-----------------------------------------------|-----------------------|
        | Photon 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | Photon 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | Photon 1 MinPt and MaxRelIsolationPt for different eta regions:       |                                   |
        |    - $0<\|\eta\|<1.479$                                               | $p_T>31.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                                 | $p_T>30.5$ GeV && $RelIsoPt<0.205$     |
        | Photon 2 MinPt and MaxRelIsolationPt for different eta regions:       |                                   |
        |    - $0<\|\eta\|<1.479$                                               | $p_T>19.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                                 | $p_T>16.9$ GeV && $RelIsoPt<0.205$     |
        | Photon 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `minDR`                                       | 0.1                   |

        - Sequence HLTDoFullUnpackingEgammaEcalL1SeededSequence
        - Sequence HLTPFClusteringForEgammaL1SeededSequence
        - Sequence HLTHgcalTiclPFClusteringForEgammaL1SeededSequence
        - EgammaHLTRecoEcalCandidateProducers
        - HLT filter: [hltEgammaCandidatesWrapperL1Seeded](./Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html) -
        This seed should select the `hltEgammaCandidatesL1Seeded` objects applying isolation condition.
        - HLT filter: [hltEG30EtL1SeededFilter](./Phase2Menu_Legacy/hltEG30EtL1SeededFilter.html) -
        This seed should select the events containing at HLT one (`ncandcut=1`) `hltEgammaCandidatesL1Seeded` object with $p_T>30$ GeV (same threshold in EB and EE).
        - HLT filter: [hltDiEG23EtL1SeededFilter](./Phase2Menu_Legacy/hltDiEG23EtL1SeededFilter.html) -
        This seed should select the events containing at HLT two (`ncandcut=2`) `hltEgammaCandidatesL1Seeded` objects with $p_T>23$ GeV (same threshold in EB and EE).
        - EgammaHLTClusterShapeProducer + HLTEgammaGenericFilter (?)
        - EgammaHLTHGCalIDVarProducer + HLTEgammaGenericFilter (`sigma2vv` ?) + HLTEgammaGenericFilter (`sigma2ww` ?) + HLTEgammaGenericQuadraticEtaFilter (`hForHOverE` ?)
        - Sequence HLTEGammaDoLocalHcalSequence
        - Sequence HLTFastJetForEgammaSequence
        - EcalUncalibRecHitProducer [+] hltEcalMultiFitUncalibRecHit
        - EcalRecHitProducer [+] hltEcalRecHit
        - FixedGridRhoProducerFastjetFromRecHit [+] hltFixedGridRhoFastjetAllCaloForEGamma
        - EgammaHLTHcalVarProducerFromRecHit [+] hltEgammaHoverEL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdHEL1SeededFilter
        - EgammaHLTEcalPFClusterIsolationProducer [+] hltEgammaEcalPFClusterIsoL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdEcalIsoL1SeededFilter
        - EgammaHLTHGCalLayerClusterIsolationProducer [+] hltEgammaHGCalLayerClusterIsoL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdHgcalIsoL1SeededFilter
        - Sequence HLTPFHcalClusteringForEgammaSequence
        - EgammaHLTHcalPFClusterIsolationProducer [+] hltEgammaHcalPFClusterIsoL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdHcalIsoL1SeededFilter

3. HLT_Diphoton30_23_IsoCaloId_Unseeded

    - Sequence **HLTBeginSequence** : same everywhere

    - Sequence **HLTDiphoton3023IsoCaloIdUnseededSequence**
        - Sequence HLTL1Sequence
        - L1 seed: [pDoubleEGEle37_24](./Phase2Menu_Legacy/DoubleEGEle3724.html) OR [pDoubleIsoTkPho22_12](./Phase2Menu_Legacy/DoubleIsoTkPho2212.html) -
        The `pDoubleEGEle37_24` seed should select the events containing at L1 two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively (but I don't see it clearly in the path).
        The `pDoubleIsoTkPho22_12` seed should select the events containing at L1 two EGamma (`CL2Photons`) with tracker isolation requirement (?) with $p_T>22$ and $p_T>12$ GeV, respectively.
        NOTE: Why are the objects called differently ("EGEle" vs "IsoTkPho") if the two paths are consuming the same collection, only changing the pT threshold and minDR?

        | Selection `pDoubleEGEle37_24`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>31.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>30.5$ GeV && $RelIsoPt<0.205$     |
        | EGamma 2 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>19.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>16.9$ GeV && $RelIsoPt<0.205$     |
        | EGamma 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `minDR`                                       | 0.1                   |

        | Selection `pDoubleIsoTkPho22_12`              | Value                 |
        |-----------------------------------------------|-----------------------|
        | Photon 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | Photon 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>17.4$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>14.9$ GeV && $RelIsoPt<0.205$     |
        | EGamma 2 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>8.2$ GeV && $RelIsoPt<0.25$       |
        |    - $\|\eta\|>1.479$                                             | $p_T>4.4$ GeV && $RelIsoPt<0.205$      |
        | EGamma 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |

        - Sequence HLTDoFullUnpackingEgammaEcalSequence
        - Sequence HLTPFClusteringForEgammaUnseededSequence
        - Sequence HLTHgcalTiclPFClusteringForEgammaUnseededSequence
        - EgammaHLTRecoEcalCandidateProducers
        - HLT filter: [hltEgammaCandidatesWrapperUnseeded](./Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html) -
        This seed should select the `hltEgammaCandidatesUnseeded` objects applying isolation condition.
        - HLT filter: [hltEG30EtUnseededFilter](./Phase2Menu_Legacy/hltEG30EtUnseededFilter.html) -
        This seed should select the events containing at HLT one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>30$ GeV (same threshold in EB and EE).
        - HLT filter: [hltDiEG23EtL1SeededFilter](./Phase2Menu_Legacy/hltDiEG23EtL1SeededFilter.html) -
        This seed should select the events containing at HLT two (`ncandcut=2`) `hltEgammaCandidatesUnseeded` objects with $p_T>23$ GeV (same threshold in EB and EE).
        
        *From here same as L1seeded*

        - EgammaHLTClusterShapeProducer + HLTEgammaGenericFilter (?)
        - EgammaHLTHGCalIDVarProducer + HLTEgammaGenericFilter (`sigma2vv` ?) + HLTEgammaGenericFilter (`sigma2ww` ?) + HLTEgammaGenericQuadraticEtaFilter (`hForHOverE` ?)
        - Sequence HLTEGammaDoLocalHcalSequence
        - Sequence HLTFastJetForEgammaSequence
        - EcalUncalibRecHitProducer [+] hltEcalMultiFitUncalibRecHit
        - EcalRecHitProducer [+] hltEcalRecHit
        - FixedGridRhoProducerFastjetFromRecHit [+] hltFixedGridRhoFastjetAllCaloForEGamma
        - EgammaHLTHcalVarProducerFromRecHit [+] hltEgammaHoverEL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdHEL1SeededFilter
        - EgammaHLTEcalPFClusterIsolationProducer [+] hltEgammaEcalPFClusterIsoL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdEcalIsoL1SeededFilter
        - EgammaHLTHGCalLayerClusterIsolationProducer [+] hltEgammaHGCalLayerClusterIsoL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdHgcalIsoL1SeededFilter
        - Sequence HLTPFHcalClusteringForEgammaSequence
        - EgammaHLTHcalPFClusterIsolationProducer [+] hltEgammaHcalPFClusterIsoL1Seeded
        - HLTEgammaGenericQuadraticEtaFilter [+] hltDiEG3023IsoCaloIdHcalIsoL1SeededFilter

4. HLT_DoubleEle23_12_Iso_L1Seeded

    - Sequence **HLTBeginSequence** : same everywhere

    - Sequence **HLTDoubleEle2312IsoL1SeededSequence**
        - Sequence HLTL1Sequence
        - L1 seed: [pDoubleEGEle37_24](./Phase2Menu_Legacy/DoubleEGEle3724.html) OR [pDoubleTkEle25_12](./Phase2Menu_Legacy/DoubleTkEle2512.html) OR [pIsoTkEleEGEle22_12](./Phase2Menu_Legacy/IsoTkEleEGEle2212.html)
        The `pDoubleEGEle37_24` seed should select the events containing at L1 two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively (but I don't see it clearly in the path).
        The `pDoubleTkEle25_12` seed should select the events containing at L1 two EGamma with tracker information (`CL2Electrons`) with $p_T>25$ and $p_T>12$ GeV, respectively.
        The `pIsoTkEleEGEle22_12` seed should select the events containing at L1 two EGamma with tracker information (one `CL2Electrons` and one `CL2Photons`) with $p_T>22$ and $p_T>12$ GeV, respectively.

        | Selection `pDoubleEGEle37_24`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>31.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>30.5$ GeV && $RelIsoPt<0.205$     |
        | EGamma 2 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>19.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>16.9$ GeV && $RelIsoPt<0.205$     |
        | EGamma 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `minDR`                                       | 0.1                   |

        | Selection `pDoubleTkEle25_12`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt for different eta regions:     |                       |
        |    - $0<\|\eta\|<1.479$                       | $p_T>20.1$ GeV        |
        |    - $\|\eta\|>1.479$                         | $p_T>19.5$ GeV        |
        | EGamma 2 MinPt for different eta regions:     |                       |
        |    - $0<\|\eta\|<1.479$                       | $p_T>9.1$ GeV         |
        |    - $\|\eta\|>1.479$                         | $p_T>9.1$ GeV         |
        | EGamma 1/2 `QualityFlags`                     | 2,0                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `maxDz`                                       | 1                     |

        | Selection `pIsoTkEleEGEle22_12`               | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>17.7$ GeV && $RelIsoPt<0.13$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>17.5$ GeV && $RelIsoPt<0.28$      |
        | EGamma 2 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>8.2$ GeV && $RelIsoPt<0.25$       |
        |    - $\|\eta\|>1.479$                                             | $p_T>4.4$ GeV && $RelIsoPt<0.205$      |
        | EGamma 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `minDR`                                       | 0.1                   |

        - Sequence HLTDoFullUnpackingEgammaEcalL1SeededSequence
        - Sequence HLTPFClusteringForEgammaL1SeededSequence
        - Sequence HLTHgcalTiclPFClusteringForEgammaL1SeededSequence
        - EgammaHLTRecoEcalCandidateProducers
        - HLT filter: [hltEgammaCandidatesWrapperUnseeded](./Phase2Menu_Legacy/hltEgammaCandidatesWrapperUnseeded.html) -
        This seed should select the `hltEgammaCandidatesUnseeded` objects applying isolation condition.
        - HLT filter: [hltEG23EtL1SeededFilter](./Phase2Menu_Legacy/hltEG23EtL1SeededFilter.html) -
        This seed should select the events containing at HLT one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>23$ GeV (same threshold in EB and EE).
        - HLT filter: [hltDiEG12EtL1SeededFilter](./Phase2Menu_Legacy/hltDiEG12EtL1SeededFilter.html) -
        This seed should select the events containing at HLT two (`ncandcut=2`) `hltEgammaCandidatesUnseeded` objects with $p_T>12$ GeV (same threshold in EB and EE).
        - EgammaHLTClusterShapeProducer + HLTEgammaGenericFilter (?)
        - EgammaHLTHGCalIDVarProducer + HLTEgammaGenericFilter (`sigma2vv` ?) + HLTEgammaGenericFilter (`sigma2ww` ?) + HLTEgammaGenericQuadraticEtaFilter (`hForHOverE` ?)
        - Sequence HLTEGammaDoLocalHcalSequence
        - Sequence HLTFastJetForEgammaSequence
        - EgammaHLTHcalVarProducerFromRecHit
        - EgammaHLTHcalVarProducerFromRecHit
        - HLTEgammaGenericQuadraticEtaFilter
        - EgammaHLTEcalPFClusterIsolationProducer
        - HLTEgammaGenericQuadraticEtaFilter
        - EgammaHLTHGCalLayerClusterIsolationProducer
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTPFHcalClusteringForEgammaSequence
        - EgammaHLTHcalPFClusterIsolationProducer
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTElePixelMatchL1SeededSequence : this is probably associating the EGamma from calo (`hltEgammaCandidatesL1Seeded`) and pixel information (`hltEgammaElectronPixelSeedsL1Seeded`)
        - Sequence HLTGsfElectronL1SeededSequence
        - HLTEgammaGenericQuadraticEtaFilter
        - HLTEgammaGenericQuadraticEtaFilter
        - HLTEgammaGenericQuadraticEtaFilter
        - HLTEgammaGenericFilter
        - HLTEgammaGenericFilter
        - EgammaHLTEleL1TrackIsolProducer
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTTrackingSequence
        - Sequence HLTItLocalRecoSequence
        - EgammaHLTElectronTrackIsolationProducers
        - HLTEgammaGenericQuadraticEtaFilter

    - Sequence **HLTEndSequence**

5. HLT_DoubleEle25_CaloIdL_PMS2_L1Seeded

    - Sequence **HLTBeginSequence** : same everywhere

    - Sequence **HLTDoubleEle25CaloIdLPMS2L1SeededSequence**
        - Sequence HLTL1Sequence
        - L1 seed: [pDoubleEGEle37_24](./Phase2Menu_Legacy/DoubleEGEle3724.html) OR [pDoubleTkEle25_12](./Phase2Menu_Legacy/DoubleTkEle2512.html) - 
        The `pDoubleEGEle37_24` seed should select the events containing at L1 two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively.
        The `pDoubleTkEle25_12` seed should select the events containing at L1 two EGamma with tracker information (`CL2Electrons`) with $p_T>25$ and $p_T>12$ GeV, respectively.

        | Selection `pDoubleEGEle37_24`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>31.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>30.5$ GeV && $RelIsoPt<0.205$     |
        | EGamma 2 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>19.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>16.9$ GeV && $RelIsoPt<0.205$     |
        | EGamma 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `minDR`                                       | 0.1                   |

        | Selection `pDoubleTkEle25_12`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt for different eta regions:     |                       |
        |    - $0<\|\eta\|<1.479$                       | $p_T>20.1$ GeV        |
        |    - $\|\eta\|>1.479$                         | $p_T>19.5$ GeV        |
        | EGamma 2 MinPt for different eta regions:     |                       |
        |    - $0<\|\eta\|<1.479$                       | $p_T>9.1$ GeV         |
        |    - $\|\eta\|>1.479$                         | $p_T>9.1$ GeV         |
        | EGamma 1/2 `QualityFlags`                     | 2,0                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `maxDz`                                       | 1                     |

        - Sequence HLTDoFullUnpackingEgammaEcalL1SeededSequence
        - Sequence HLTPFClusteringForEgammaL1SeededSequence
        - Sequence HLTHgcalTiclPFClusteringForEgammaL1SeededSequence

        - HLT filter: [hltEgammaCandidatesWrapperL1Seeded](./Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html) -
        This seed should select the `hltEgammaCandidatesL1Seeded` objects applying isolation condition.
        - HLT filter: [hltDiEG25EtL1SeededFilter](./Phase2Menu_Legacy/hltDiEG25EtL1SeededFilter.html) -
        This seed should select the events containing at HLT one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>25$ GeV (same threshold in EB and EE).
        
        - EgammaHLTClusterShapeProducer + HLTEgammaGenericFilter (?)
        - EgammaHLTHGCalIDVarProducer + HLTEgammaGenericFilter (`sigma2vv` ?)
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTEGammaDoLocalHcalSequence
        - EgammaHLTHcalVarProducerFromRecHit
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTElePixelMatchL1SeededSequence
        - HLTElectronPixelMatchFilter
        - HLTEgammaGenericFilter
    
    - Sequence **HLTEndSequence**

6. HLT_DoubleEle25_CaloIdL_PMS2_Unseeded

    - Sequence **HLTBeginSequence** : same everywhere

    - Sequence **HLTDoubleEle25CaloIdLPMS2L1SeededSequence**
        - Sequence HLTL1Sequence
        - L1 seed: [pDoubleEGEle37_24](./Phase2Menu_Legacy/DoubleEGEle3724.html) OR [pDoubleTkEle25_12](./Phase2Menu_Legacy/DoubleTkEle2512.html) - 
        The `pDoubleEGEle37_24` seed should select the events containing at L1 two EGamma (`CL2Photons`) with $p_T>37$ and $p_T>24$ GeV, respectively.
        The `pDoubleTkEle25_12` seed should select the events containing at L1 two EGamma with tracker information (`CL2Electrons`) with $p_T>25$ and $p_T>12$ GeV, respectively.

        | Selection `pDoubleEGEle37_24`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>31.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>30.5$ GeV && $RelIsoPt<0.205$     |
        | EGamma 2 MinPt and MaxRelIsolationPt for different eta regions:   |                                        |
        |    - $0<\|\eta\|<1.479$                                           | $p_T>19.2$ GeV && $RelIsoPt<0.25$      |
        |    - $\|\eta\|>1.479$                                             | $p_T>16.9$ GeV && $RelIsoPt<0.205$     |
        | EGamma 1/2 `QualityFlags`                     | 2,4                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `minDR`                                       | 0.1                   |

        | Selection `pDoubleTkEle25_12`                 | Value                 |
        |-----------------------------------------------|-----------------------|
        | EGamma 1 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 2 $\eta$ region                        | $\|\eta\| < 2.4$      |
        | EGamma 1 MinPt for different eta regions:     |                       |
        |    - $0<\|\eta\|<1.479$                       | $p_T>20.1$ GeV        |
        |    - $\|\eta\|>1.479$                         | $p_T>19.5$ GeV        |
        | EGamma 2 MinPt for different eta regions:     |                       |
        |    - $0<\|\eta\|<1.479$                       | $p_T>9.1$ GeV         |
        |    - $\|\eta\|>1.479$                         | $p_T>9.1$ GeV         |
        | EGamma 1/2 `QualityFlags`                     | 2,0                   |
        | `cos_phi_lut`                                 | ?                     |
        | `cosh_eta_lut`                                | ?                     |
        | `cosh_eta_lut2`                               | ?                     |
        | `GTTPrimaryVert`                              | ?                     |
        | `inv_mass_checks`                             | False                 |
        | `maxDz`                                       | 1                     |

        - Sequence HLTDoFullUnpackingEgammaEcalL1SeededSequence
        - Sequence HLTPFClusteringForEgammaL1SeededSequence
        - Sequence HLTHgcalTiclPFClusteringForEgammaL1SeededSequence

        - HLT filter: [hltEgammaCandidatesWrapperL1Seeded](./Phase2Menu_Legacy/hltEgammaCandidatesWrapperL1Seeded.html) -
        This seed should select the `hltEgammaCandidatesL1Seeded` objects applying isolation condition.
        - HLT filter: [hltDiEG25EtL1SeededFilter](./Phase2Menu_Legacy/hltDiEG25EtL1SeededFilter.html) -
        This seed should select the events containing at HLT one (`ncandcut=1`) `hltEgammaCandidatesUnseeded` object with $p_T>25$ GeV (same threshold in EB and EE).
        
        - EgammaHLTClusterShapeProducer + HLTEgammaGenericFilter (?)
        - EgammaHLTHGCalIDVarProducer + HLTEgammaGenericFilter (`sigma2vv` ?)
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTEGammaDoLocalHcalSequence
        - Sequence HLTFastJetForEgammaSequence (added wrt L1Seeded)
        - EgammaHLTHcalVarProducerFromRecHit
        - HLTEgammaGenericQuadraticEtaFilter
        - Sequence HLTElePixelMatchL1SeededSequence
        - HLTElectronPixelMatchFilter
        - HLTEgammaGenericFilter
    
    - Sequence **HLTEndSequence**

7. HLT_DoubleMediumChargedIsoPFTauHPS40_eta2p1

    - Sequence **HLTBeginSequence** 

    - L1 seed: [pDoublePuppiTau52_52](./Phase2Menu_Legacy/DoublePuppiTau5252.html)
    This seed should select the events containing at L1 a single PUPPI jet with $p_T>230$ GeV (but I don't see it in the path).
    
    | Selection                                     | Value                 |
    |-----------------------------------------------|-----------------------|
    | $\eta$ region                                 | $\|\eta\| < 2.172$    |
    | `GTTPrimaryVert`                              | ?                     |
    | Different MinPt for different eta regions:    |                       |
    |    - $0<\|\eta\|<1.5$                         | $p_T>166.1$ GeV       |
    |    - $1.5<\|\eta\|<2.4$                       | $p_T>128.51$ GeV      |
    |    - $\|\eta\|>2.4$                           | $p_T>139.1$ GeV       | -->
