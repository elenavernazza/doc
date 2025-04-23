# CMSSW commands I will forget

| Command                       | Usage                                                             |
|-------------------------------|-------------------------------------------------------------------|
| `scram l`                     | List all CMSSW releases                                           |
| `scram b -j 8`                | Compile                                                           |
| `git cms-init`                | Links the CMSSW release to my private CMSSW fork                  |
| `git cms-addpkg <pkg_name>`   | Add package you want to modify                                    |
| `runTheMatrix.py`             | List and get the HLT configurations                               |
| `edmConfigDump step.py > file.txt` | Print all configuration in one long file                     |
| `git cms-checkdeps`           | List all packages that inherit from the Dataformat you changed    |
| `git cms-checkdeps -a -A`     | Download only the missing packages that depend on your changes    |
| `git cms-rebase-topic`        | Rebase but safer                                                  |
| `scram b code-format`         | Good indentation                                                  |

## Other instructions

* Activate the cmssw environment on the openlab machines with: 
```bash
source /cvmfs/cms.cern.ch/cmsset_default.sh
```

## Errors

* `undefined reference to 'VTT for SimpleTrackValidationPtBins'` <br>
The distructor is not well defined. Replace `~SimpleTrackValidationPtBins() override;` with `~SimpleTrackValidationPtBins() override = default;`