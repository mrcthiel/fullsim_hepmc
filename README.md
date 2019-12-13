### Instructions to run the fullsim with hepmc input

- Set the release:
> cmsrel CMSSW_9_4_13

> cd CMSSW_9_4_13/src

> cmsenv

- Clone the repositorie
> git clone git@github.com:mrcthiel/fullsim_hepmc.git

> mv fullsim_hepmc/* .

> scram b -j8

- Copy a hepmc file example:
> cp /afs/cern.ch/user/m/mthiel/private/hepmc.hepmc .

The inputHepMC EDFilter is placed in the directory inputHepMC/. **It just works for FPMC and WW and ZZ process.** One can define the decay channel in the GEN-SIM step setting the number of muons, electron, and quarks decay particles. For example, the semileptonic channel, considering muon as a lepton, can be run like this: 

> cmsRun GEN-SIM.py nM=1 nE=0 nQ=2

for the next steps just do:

> cmsRun step1_DIGIPREMIX_S2_DATAMIX_L1_DIGI2RAW_HLT.py

> cmsRun step2_RAW2DIGI_RECO_RECOSIM_EI.py # it produces the AOD file

> cmsRun step1_PAT.py # it produces the miniAOD file

**These files are basically the same used in the RunIIFall17 Campaign.**

**To run high statistics one has to add more minimum bias files in the step1_DIGIPREMIX_S2_DATAMIX_L1_DIGI2RAW_HLT.py config file.**


